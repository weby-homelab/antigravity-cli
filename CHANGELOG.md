# Antigravity CLI Changelog

The terminal-first surface to interact with Antigravity agents. Stay in your flow without context switching.

## 1.0.2

- Added `AGY_CLI_HIDE_ACCOUNT_INFO` environment variable to hide email and plan tier from the header.
- Fixed timeout overrides: restricted the default 60-second interaction timeout specifically to subagents, preventing the main agent from being unconditionally capped.
- Fixed a nil-pointer panic in Sandbox Mode: resolved a typed nil interface comparison when fetching URL content.
- Fixed fallback skill discovery in Standalone mode: ensures custom/fallback skills are successfully loaded even if the standard configuration directory is missing, and added automatic path deduplication to prevent duplicates.
- Fixed command rendering in message history: prefixed slash commands with a caret (`>`) in response block headers to clearly distinguish user-typed commands from agent outputs.
- Fixed plugin installation path mismatch: updated the `plugin` subcommand to install downloaded plugins directly to the shared configuration directory (`~/.gemini/config/`) rather than the private application data folder, making them instantly discoverable.
- Fixed Git short-hash support in diff selection: updated the commit hash recognition pattern in the  /diff  commit selection tree to match Git's standard 7-character short hashes (and up to 40-character full hashes).
- Fixed statusline subcommand handling and recursive loops: added case-insensitive subcommand parsing (help, delete, reset, enable/on, disable/off) to the /statusline command, providing direct control to toggle or revert custom statuslines and blocking recursive shell hangs during help queries.
- Improved `/help` shortcuts tab by sorting shortcuts by keybinding key, adding missing keybindings (like `ctrl+r`, `ctrl+o`, `alt+j`, `ctrl+k`), and generalizing scrolling (PageUp/PageDown/GoToTop/GoToBottom) for both Commands and Shortcuts tabs.

## 1.0.1

- Fixed OAuth token persistence and authentication hangs.
- Fixed Windows log redirection and resizing issues. Resolved a critical bug where logs were not redirected correctly on Windows, which previously caused the terminal to swallow window resize events and shut down slowly.
- Added `proceed-in-sandbox` tool permission mode. Auto-approves terminal commands that run inside the secure sandbox, requesting manual approval only when a command attempts to bypass the sandbox.
- Integrates consumer/free-tier onboarding directly into the CLI.
- Added plugin discovery for skills and agents. Automatically scans installed plugin directories to make custom skills and specialized agents available for execution in the CLI.
- Fixed pasted text line counting. Corrected line counting for user inputs to ensure extremely long inputs are correctly folded into a `[Pasted text #X +Y lines]` placeholder to keep the viewport clean.
- Fixed onboarding stability. Resolved a race condition where a concurrent terminal resize event during onboarding could revert the UI to a blank onboarding screen.
- Moves the **terminal** color scheme to the top of the selection list, making it the default choice during onboarding and in `/settings`.
- Improved `/usage` and `/quota` commands. Forces a real-time reload of model configuration and remaining quotas, allowing you to see updated real-time consumption statistics immediately.
- Improved step rendering layout. Calculates available terminal width dynamically and uses middle-truncation (`/foo/.../bar`) for file path tools to prevent layout shifting on narrow screens.
- Improved session deletion keybinding in `/resume`. Changed the shortcut from `ctrl+d` to `ctrl+delete` to resolve conflicts with the global exit keybinding (`ctrl+d` `ctrl+d`) and preserve Emacs-style forward-delete in search input fields.
- Restored automatic table wrapping, preventing long cells inside markdown tables from being truncated.
- Resolved an issue where deleted files (represented by `+++ /dev/null`) had their deletion lines incorrectly merged into the previous file's diff.

## 1.0.0

- Initial release of the Antigravity CLI.
