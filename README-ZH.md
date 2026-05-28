<p align="center">
  <a href="README.md">English</a> | <b>中文</b> | <a href="README-ES.md">Español</a> | <a href="README-FR.md">Français</a> | <a href="README-PT.md">Português</a> | <a href="README-UA.md">Українська</a> | <a href="README-DE.md">Deutsch</a>
</p>

# Antigravity CLI

Antigravity CLI 能够理解您的代码库、在获得您许可的情况下编辑文件并执行命令——直接在您的终端中进行。

- **官方文档**: [antigravity.google/docs/cli-overview](https://antigravity.google/docs/cli-overview)
- **官方网站**: [antigravity.google/product/antigravity-cli](https://antigravity.google/product/antigravity-cli)

![Antigravity CLI Demo](agy-cli-demo.gif)

---

Antigravity CLI 将 Antigravity 2.0 的核心能力（多步推理、多文件编辑、工具调用和持久化历史记录）直接带入您的终端。它针对键盘驱动的常规工作流以及具有极低资源开销的远程 SSH 会话进行了优化。

---

## 功能概览

| 功能 | Antigravity CLI | Antigravity 2.0 |
| :--- | :--- | :--- |
| **主要侧重点** | 速度、键盘效率、低开销 | 全面性、可视化编排、项目管理 |
| **界面** | 终端用户界面 (TUI) | 完整丰富的 GUI 应用程序 |
| **工作流** | SSH/远程会话，键盘优先 | 本地工作区，重度编排 |
| **智能体引擎** | 共享核心智能体引擎 | 共享核心智能体引擎 |

---

## 整合与协同

- **共享智能体引擎**: 两种界面均运行在相同的核心智能体引擎上。改进将自动应用到两者。
- **共享设置**: 偏好设置和权限进行双向同步。
- **会话导出**: 将终端会话导出至 Antigravity 2.0 GUI 以继续工作。

---

## 安装

### macOS / Linux
```bash
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

### Windows PowerShell
```powershell
irm https://antigravity.google/cli/install.ps1 | iex
```

### Windows CMD
```cmd
curl -fsSL https://antigravity.google/cli/install.cmd -o install.cmd && install.cmd && del install.cmd
```

---

## 身份验证

CLI 通过系统钥匙串进行身份验证，如果不存在活动会话，则回退到 Google 登录。

- **本地**: 自动打开您的默认浏览器。
- **远程 / SSH**: 检测 SSH 会话并打印授权 URL，以便在本地完成登录。
- **退出登录**: 运行 `/logout` 以清除保存的凭据。

> [!NOTE]
> 如需企业访问，请在新手引导期间连接您的 GCP 项目。详情请参阅企业版页面。

---

## 服务条款与数据使用

> [!WARNING]
> 众所周知，AI 编码智能体存在一定的安全风险，包括自主代码执行、数据外泄、提示词注入以及供应链风险。请务必监控并验证智能体执行的所有操作。

通过使用 Antigravity CLI，您同意允许 Google 收集并使用您的交互数据以帮助改善产品，这受 Google 服务条款和 Google 隐私权政策的约束。您可以随时通过设置选择退出。

### 法律与隐私链接

- **服务条款**: [antigravity.google/terms](https://antigravity.google/terms)
- **隐私权政策**: [policies.google.com/privacy](https://policies.google.com/privacy)
