# 🚀 Antigravity CLI

[![Fork](https://img.shields.io/badge/fork-google--antigravity-blue?logo=github)](https://github.com/google-antigravity/antigravity-cli)
[![Version](https://img.shields.io/badge/version-1.0.2-green)](CHANGELOG.md)
[![License](https://img.shields.io/badge/license-Proprietary-orange)](https://antigravity.google/terms)
[![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20macOS%20%7C%20Windows-lightgrey)]()

> **AI-агент прямо у вашому терміналі** — розуміє кодову базу, редагує файли з вашого дозволу та виконує команди.

![Antigravity CLI Demo](agy-cli-demo.gif)

---

## ⚡ Швидкий старт

### Встановлення

<details open>
<summary><b>Linux / macOS</b></summary>

```bash
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

Або з цього репозиторію:
```bash
git clone https://github.com/weby-homelab/antigravity-cli.git
cd antigravity-cli
make install
```
</details>

<details>
<summary><b>Windows PowerShell</b></summary>

```powershell
irm https://antigravity.google/cli/install.ps1 | iex
```
</details>

<details>
<summary><b>Windows CMD</b></summary>

```cmd
curl -fsSL https://antigravity.google/cli/install.cmd -o install.cmd && install.cmd && del install.cmd
```
</details>

### Перший запуск

```bash
# Запустити інтерактивний режим
agy

# Виконати одну команду
agy -p "Поясни архітектуру цього проєкту"

# Продовжити останню розмову
agy -c
```

---

## 📋 Можливості

| Можливість | Опис |
|:---|:---|
| **Мульти-файлове редагування** | Редагує декілька файлів одночасно з вашим підтвердженням |
| **Shell-команди** | Виконує термінальні команди в sandbox або напряму |
| **Мульти-степ reasoning** | Планує та виконує складні задачі крок за кроком |
| **Persistent history** | Зберігає контекст розмов між сесіями |
| **Plugin system** | Розширення через плагіни та кастомні skills |
| **SSH/Remote** | Оптимізований для SSH-сесій та headless середовищ |

---

## ⚙️ Конфігурація

### Файл проєкту `.antigravity.md`

Створіть `.antigravity.md` у корені проєкту для кастомних інструкцій:

```markdown
# Project Context

This is a Python FastAPI project using Pydantic v2.
Always use `model_dump()` instead of deprecated `dict()`.
Database: PostgreSQL with SQLAlchemy 2.0 async.
Tests: pytest with async fixtures.
```

### Налаштування (`~/.gemini/settings.json`)

```json
{
  "theme": "terminal",
  "sandbox": false,
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"]
    }
  }
}
```

### Agents (`~/.antigravity/agents/`)

Створюйте спеціалізованих агентів у YAML:

```yaml
# ~/.antigravity/agents/reviewer.yaml
name: code-reviewer
description: "Reviews code for security and best practices"
instructions: |
  Review the code for:
  - Security vulnerabilities
  - Performance issues
  - Code style violations
```

---

## 🔐 Автентифікація

| Метод | Опис |
|:---|:---|
| **Google Sign-In** | За замовчуванням, відкриває браузер. Free tier: 60 req/min, 1000 req/day |
| **SSH/Remote** | Виводить URL для авторизації на іншому пристрої |
| **API Key** | `export GEMINI_API_KEY="YOUR_KEY"` |
| **Vertex AI** | `export GOOGLE_GENAI_USE_VERTEXAI=true` для enterprise |
| **Вихід** | Команда `/logout` |

---

## 🔧 Команди

```bash
agy                              # Інтерактивний режим
agy -p "запит"                   # Одноразовий запит (non-interactive)
agy -c                           # Продовжити останню розмову
agy --conversation <ID>          # Відновити конкретну розмову
agy --sandbox                    # Запуск у пісочниці
agy --add-dir ../lib             # Додати директорію до workspace
agy update                       # Оновити до останньої версії
agy changelog                    # Показати changelog
agy plugin list                  # Показати встановлені плагіни
agy plugin install <name>        # Встановити плагін
```

### Slash-команди (в інтерактивному режимі)

| Команда | Опис |
|:---|:---|
| `/help` | Показати довідку |
| `/settings` | Відкрити налаштування |
| `/usage`, `/quota` | Статистика використання |
| `/diff` | Переглянути git diff |
| `/resume` | Відновити попередню сесію |
| `/logout` | Вийти з акаунту |
| `/statusline` | Налаштувати статус-бар |

---

## 🔄 Міграція з Gemini CLI

> ⚠️ **Gemini CLI (`gemini`) припиняє роботу 18 червня 2026** для non-enterprise користувачів.

### Кроки міграції

```bash
# 1. Встановити Antigravity CLI
curl -fsSL https://antigravity.google/cli/install.sh | bash

# 2. Перейменувати конфіг-файли
mv GEMINI.md .antigravity.md
mv .gemini/agents/ .antigravity/agents/   # якщо є

# 3. Оновити CI/CD скрипти
# Замінити 'gemini' → 'agy' в усіх скриптах

# 4. Видалити старий Gemini CLI
npm uninstall -g @google/gemini-cli
```

### Порівняння

| | Gemini CLI (deprecated) | Antigravity CLI |
|:---|:---|:---|
| **Мова** | Node.js/TypeScript | Go (native binary) |
| **Команда** | `gemini` | `agy` |
| **Інсталяція** | `npm install -g` | `curl \| bash` (175MB binary) |
| **Конфіг** | `GEMINI.md` | `.antigravity.md` |
| **Агенти** | `.gemini/agents/` | `.antigravity/agents/` |
| **Оновлення** | `npm update` | `agy update` (self-update) |
| **Статус** | ⛔ EOL 18.06.2026 | ✅ Активна розробка |

---

## 📁 Структура репозиторію

```
antigravity-cli/
├── install.sh           # Інсталятор для Linux/macOS
├── install.ps1          # Інсталятор для Windows PowerShell
├── install.cmd          # Інсталятор для Windows CMD
├── Makefile             # make install / make update / make uninstall
├── .antigravity.md      # Шаблон конфігу проєкту
├── README.md            # Цей файл
├── CHANGELOG.md         # Журнал змін
└── agy-cli-demo.gif     # Демо-анімація
```

---

## 🤝 Contributing

Це community-форк [google-antigravity/antigravity-cli](https://github.com/google-antigravity/antigravity-cli).

Ми додаємо:
- 🇺🇦 Українську документацію та локалізацію
- 📖 Розширені гайди з міграції та конфігурації
- 🔧 Makefile та утиліти для зручної установки
- 🐛 Баг-фікси та PR до upstream

---

## 📜 Legal

- **Official Docs**: [antigravity.google/docs/cli-overview](https://antigravity.google/docs/cli-overview)
- **Terms of Service**: [antigravity.google/terms](https://antigravity.google/terms)
- **Privacy Policy**: [policies.google.com/privacy](https://policies.google.com/privacy)

> [!WARNING]
> AI coding agents мають ризики: автономне виконання коду, data exfiltration, prompt injection. Завжди перевіряйте дії агента.
