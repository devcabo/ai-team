# AI Team

A Windows terminal interface for coordinating multiple AI command-line agents, with automatic routing, parallel delegation, project workspaces, and editable local SQLite memory.

> AI Team does **not** include AI subscriptions, provider accounts, or model access. Install and authenticate compatible provider CLIs separately.

## Install (Windows)

**Requirements:** Windows 10/11, PowerShell 5.1+, Node.js **22.13+** (Node.js 24 LTS recommended), and at least one supported authenticated AI CLI. Administrator privileges are not required.

1. Download this repository as a ZIP using **Code → Download ZIP**, or clone it with Git.
2. Extract the project.
3. Open PowerShell in the folder containing `install.ps1` and run:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File .\install.ps1
```

4. Open a **new** PowerShell window and start the app:

```powershell
ait
```

If `node` is not on PATH, you can use portable Node.js by placing `node.exe` in `$HOME\Tools\NodeJS\node.exe`. The installer checks syntax and runs the test suite before replacing an existing installation, keeping a backup.

**Note:** The source files must be uploaded to this repository before the installation steps above will work. A README alone is not an installable application.

## Configure AI agents

```powershell
ait providers
ait providers setup
ait providers add
```

Supported integrations include Claude, Codex, Antigravity and configurable generic CLI providers, subject to local installation and authentication. A provider marked READY may still require an authenticated session.

## How routing works

Simple greetings and short questions use one suitable agent to avoid unnecessary latency. Complex implementation tasks can delegate to multiple available agents; explicit requests for all agents are supported. The activity panel should distinguish active, queued, idle, completed and failed agents. Percentages must not imply progress that cannot be measured.

## Local memory

Open **F4 → memory** to edit identity, agent roles, skills, projects, sessions, knowledge and system workflows. Local files live under `%USERPROFILE%\.ait`, including the SQLite memory database, projects and provider settings. These files are **not part of the public source**.

## Commands

```powershell
ait
ait providers
ait doctor
ait memory list
ait memory export
```

Within the app: `/help`, `/effort auto|low|medium|high|xhigh`, F2 (quota), F3 (mods), F4 (memory).

## Development

```powershell
node --test
```

Automated tests do not guarantee real-world provider authentication, Windows terminal behavior or network availability.

## Privacy and security

Never commit local memory, logs, workspaces, `.env` files, access tokens, corporate files or credentials. Review changes before publishing, and follow your organization's software policies. See `SECURITY.md` for reporting guidance.

## License

MIT — see `LICENSE`.
