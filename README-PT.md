<p align="center">
  <a href="README.md">English</a> | <a href="README-ZH.md">中文</a> | <a href="README-ES.md">Español</a> | <a href="README-FR.md">Français</a> | <b>Português</b> | <a href="README-UA.md">Українська</a> | <a href="README-DE.md">Deutsch</a>
</p>

# Antigravity CLI

Antigravity CLI compreende a sua base de código, faz edições com a sua permissão e executa comandos — diretamente do seu terminal.

- **Documentação Oficial**: [antigravity.google/docs/cli-overview](https://antigravity.google/docs/cli-overview)
- **Website Oficial**: [antigravity.google/product/antigravity-cli](https://antigravity.google/product/antigravity-cli)

![Antigravity CLI Demo](agy-cli-demo.gif)

---

O Antigravity CLI traz os recursos principais do Antigravity 2.0 (raciocínio em várias etapas, edição de vários arquivos, chamadas de ferramentas e histórico persistente) diretamente para o seu terminal. Ele é otimizado para fluxos de trabalho orientados por teclado e sessões SSH remotas com sobrecarga mínima de recursos.

---

## Visão Geral dos Recursos

| Recurso | Antigravity CLI | Antigravity 2.0 |
| :--- | :--- | :--- |
| **Foco Principal** | Velocidade, eficiência do teclado, baixa sobrecarga | Abrangência, orquestração visual, gerenciamento de projetos |
| **Interface** | Interface de Usuário de Terminal (TUI) | Aplicativo GUI Completo e Rico |
| **Fluxos de Trabalho** | Sessões SSH/remotas, primeiro o teclado | Espaços de trabalho locais, orquestração pesada |
| **Motor de Agente** | Motor de Agente Central Compartilhado | Motor de Agente Central Compartilhado |

---

## Integração

- **Motor de Agente Compartilhado**: Ambas as interfaces rodam no mesmo motor de agente central. As melhorias se aplicam automaticamente a ambas.
- **Configurações Compartilhadas**: As preferências e as permissões são sincronizadas bidirecionalmente.
- **Exportação de Sessão**: Exporte sessões de terminal para a GUI do Antigravity 2.0 para continuar trabalhando.

---

## Instalação

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

## Autenticação

A CLI se autentica por meio do chaveiro do sistema, recorrendo ao login do Google se não houver sessão ativa.

- **Local**: Abre automaticamente o seu navegador padrão.
- **Remoto / SSH**: Detecta sessões SSH e exibe uma URL de autorização para concluir o login localmente.
- **Sair**: Execute `/logout` para limpar as credenciais salvas.

> [!NOTE]
> Para acesso corporativo, conecte seu projeto do GCP durante a integração. Consulte la página de Enterprise para obter mais detalhes.

---

## Termos de Serviço e Uso de Dados

> [!WARNING]
> Sabe-se que os agentes de codificação de IA apresentam certos riscos de segurança, incluindo execução autônoma de código, exfiltração de dados, injeção de prompt e riscos na cadeia de suprimentos. Certifique-se de monitorar e verificar todas as ações tomadas pelo agente.

Ao usar o Antigravity CLI, você concorda em ajudar a melhorar o produto, permitindo que a Google colete e use seus dados de interações, sujeito aos Termos de Serviço da Google e à Política de Privacidade da Google. Você pode optar por sair a qualquer momento por meio de suas configurações.

### Links Legais e de Privacidade

- **Termos de Serviço**: [antigravity.google/terms](https://antigravity.google/terms)
- **Política de Privacidade**: [policies.google.com/privacy](https://policies.google.com/privacy)
