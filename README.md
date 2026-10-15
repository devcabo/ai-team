# AI Team

**One terminal. Your own AI team. Your own editable memory.**

AI Team is a Windows terminal interface that coordinates multiple locally installed AI command-line tools. It supports automatic agent selection, delegation, parallel execution, Markdown rendering, local SQLite memory, and project workflows.

## Requirements

- Windows 10/11 with PowerShell 5.1 or later
- Node.js 22.13+ (portable Node.js works; administrator access is not required)
- At least one supported AI CLI installed and authenticated separately

## Installation

1. Download or clone this repository.
2. Put portable `node.exe` in `$HOME\Tools\NodeJS\node.exe`, or install Node.js 22.13+ on your PATH.
3. From the downloaded project folder, run:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File .\install.ps1
```

4. Open a new PowerShell window and run:

```powershell
ait
```

The installer installs under your Windows user profile, runs tests before replacing an existing installation, and does not require administrator privileges.

## Providers

```powershell
ait providers
ait providers setup
ait providers add
```

Supported integrations include Claude (Sonnet and Opus), Codex and Antigravity, subject to CLI availability and authentication. Provider availability depends on your local setup. An agent marked READY is not a guarantee of a valid remote session.

## Memory and projects

AI Team stores editable local memory and project context using SQLite. Open the memory interface in the app to inspect and edit entries. **Your personal memory database, credentials, sessions and workspaces are not included in this repository.**

## Usage

Run `ait` and choose a project. Simple prompts can use one agent; more complex tasks can delegate to multiple configured agents. The effort setting guides supported providers. CLI flags and capabilities vary by provider.

## Privacy and security

- Never commit `.env` files, credentials, local configuration, chat logs, or personal memory databases.
- Review scripts before execution.
- Authentication to third-party AI services is managed by their respective CLIs.
- No credentials are bundled with this project.

## Development

```powershell
node --test
```

## License

MIT. See [LICENSE](LICENSE).
