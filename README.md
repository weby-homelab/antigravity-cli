# Antigravity CLI

Antigravity CLI understands your codebase, makes edits with your permission, and executes commands — right from your terminal.

- **Official Docs**: [antigravity.google/docs/cli-overview](https://antigravity.google/docs/cli-overview)
- **Official Website**: [antigravity.google/product/antigravity-cli](https://antigravity.google/product/antigravity-cli)

![Antigravity CLI Demo](agy-cli-demo.gif)

---

Antigravity CLI brings the core capabilities of Antigravity 2.0 (multi-step reasoning, multi-file editing, tool calling, and persistent history) directly to your terminal. It is optimized for keyboard-driven workflows and remote SSH sessions with minimal resource overhead.

---

## Features at a Glance

| Feature | Antigravity CLI | Antigravity 2.0 |
| :--- | :--- | :--- |
| **Primary Focus** | Speed, keyboard efficiency, low overhead | Comprehensiveness, visual orchestration, project management |
| **Interface** | Terminal User Interface (TUI) | Full Rich GUI Application |
| **Workflows** | SSH/Remote sessions, keyboard-first | Local workspaces, heavy orchestration |
| **Agent Engine** | Shared Core Agent Engine | Shared Core Agent Engine |

---

## Integration

- **Shared Agent Engine**: Both interfaces run on the same core agent engine. Improvements automatically apply to both.
- **Shared Settings**: Preferences and permissions sync bidirectionally.
- **Session Export**: Export terminal sessions to the Antigravity 2.0 GUI to continue working.

---

## Installation

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

## Authentication

The CLI authenticates via the system keyring, falling back to Google Sign-In if no active session exists.

- **Local**: Automatically opens your default browser.
- **Remote / SSH**: Detects SSH sessions and prints an authorization URL to complete login locally.
- **Sign Out**: Run `/logout` to clear saved credentials.

> [!NOTE]
> For enterprise access, connect your GCP project during onboarding. See the Enterprise page for details.

---

## Customization

### Custom Status Line

By default, the CLI displays a minimal status bar showing only `? for shortcuts` and the current model name. You can replace it with a fully dynamic status line that shows agent state, context window usage, Git branch, active subagents, and more.

**Quick setup** — automatically copy and configure the statusline script:

```bash
bash examples/statusline/setup.sh
```

Or configure it manually in your settings (accessible via `/settings` in the CLI, or by editing the settings file directly):

```json
{
  "statusLine": {
    "command": "/absolute/path/to/statusline.sh",
    "enabled": true
  }
}
```

> [!TIP]
> The settings file location varies by platform:
> - **Linux**: `~/.gemini/antigravity-cli/settings.json`
> - **macOS**: `~/Library/Application Support/antigravity-cli/settings.json`
> - **Windows**: `%APPDATA%\antigravity-cli\settings.json`
>
> You can also open settings interactively by typing `/settings` inside the CLI.

The script receives a JSON payload on stdin with the current agent state and outputs formatted ANSI text. See [`examples/statusline/`](examples/statusline/) for the full reference implementation.

### Custom Window Title

Similarly, you can set a dynamic terminal window title that reflects the agent's current state (thinking, tool use, idle) and workspace.

**Quick setup** — automatically copy and configure the title script:

```bash
bash examples/title/setup.sh
```

Or configure it manually in your settings:

```json
{
  "title": {
    "command": "/absolute/path/to/title.sh",
    "enabled": true
  }
}
```

See [`examples/title/`](examples/title/) for details.

> [!NOTE]
> Both scripts require [`jq`](https://jqlang.org/) to be installed. Most Linux distributions include it by default; on macOS, install via `brew install jq`.

---

## Terms of Service & Data Use

> [!WARNING]
> AI coding agents are known to have certain security risks, including autonomous code execution, data exfiltration, prompt injection, and supply chain risks. Ensure that you monitor and verify all actions taken by the agent.

By using Antigravity CLI, you agree to help improve the product by allowing Google to collect and use your Interactions data, subject to the Google Terms of Service and Google Privacy Policy. You can choose to opt out at any time via your settings.

### Legal & Privacy Links

- **Terms of Service**: [antigravity.google/terms](https://antigravity.google/terms)
- **Privacy Policy**: [policies.google.com/privacy](https://policies.google.com/privacy)
