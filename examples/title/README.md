# CLI Title Example

This directory contains an example script (`title.sh`) that demonstrates how to dynamically customize the window title for the Antigravity CLI based on the agent's current state.

For more details on how to use and configure the title script, please refer to the official public documentation:
[https://antigravity.google/docs/cli-title](https://antigravity.google/docs/cli-title)

## Quick Start

### Option 1: Automatic Setup (Recommended)

Run the included setup script from the root of the repository:

```bash
bash examples/title/setup.sh
```

This script will automatically:
1. Copy `title.sh` to your platform's global settings directory (so it stays configured even if you move or delete this repository).
2. Configure and enable it in your global `settings.json` file.

### Option 2: Manual configuration

1. Copy `title.sh` to a directory of your choice.
2. Edit your `settings.json` file to point `title.command` to the absolute path of `title.sh` and set `title.enabled` to `true`:

```json
{
  "title": {
    "command": "/absolute/path/to/title.sh",
    "enabled": true
  }
}
```

**Settings file locations:**

| Platform | Path |
| :--- | :--- |
| Linux | `~/.gemini/antigravity-cli/settings.json` |
| macOS | `~/Library/Application Support/antigravity-cli/settings.json` |
| Windows | `%APPDATA%\antigravity-cli\settings.json` |

> [!IMPORTANT]
> The `command` field must be an **absolute path** to the script. Relative paths and `~` expansion are not supported.

After saving, restart `agy` for changes to take effect.

## How it works

The `title.sh` script reads a JSON payload from standard input, which contains real-time information about the agent's state and context. It then:
1. Extracts the `agent_state` and `workspace.current_dir` using `jq`.
2. Parses the current directory to determine a short workspace name (with special handling for CitC workspaces).
3. Maps the agent state to a corresponding emoji (e.g., 🤔 for thinking, 🛠️ for tool use, 😴 for idle).
4. Outputs the formatted title string in the format: `[Emoji] [State] | [Workspace]`.

## Examples

### Idle State
![Idle State Title](images/title-idle.png)

### Review Mode
![Review Mode Title](images/title-review.png)

### Tool Confirmation
![Tool Confirmation Title](images/title-tool-confirmation.png)
