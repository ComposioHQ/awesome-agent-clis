---
name: "Google Suite CLI (gogcli)"
description: "CLI for Gmail, Calendar, Chat, Drive, Docs, Sheets, Slides, Forms, Contacts, Tasks, Keep, and Admin. Use when an agent needs to interact with any Google Workspace service — send emails, manage calendar events, search Drive, read/write spreadsheets, or manage contacts."
---

# gogcli — Google in your terminal

Fast, script-friendly CLI for Gmail, Calendar, Chat, Classroom, Drive, Docs, Slides, Sheets, Forms, Apps Script, Contacts, Tasks, People, Admin, Groups, and Keep.

- **Repo**: https://github.com/steipete/gogcli
- **Author**: [@steipete](https://github.com/steipete)

## Installation

```bash
brew install gogcli
```

Or build from source:

```bash
git clone https://github.com/steipete/gogcli.git
cd gogcli && make
```

## Authentication

Requires OAuth2 credentials from Google Cloud Console:

```bash
# Store OAuth client credentials (one-time)
gog auth credentials ~/Downloads/client_secret_....json

# Authorize an account
gog auth add you@gmail.com

# Set default account
export GOG_ACCOUNT=you@gmail.com

# Verify
gog gmail labels list
```

For headless/CI environments, use `--manual` or `--remote` auth flows, or pass `--access-token` directly.

## Key Commands

### Gmail

```bash
gog gmail search "from:boss subject:urgent"
gog gmail search "is:unread" --max 10 --json
gog gmail send --to recipient@example.com --subject "Hello" --body "Message body"
gog gmail send --to recipient@example.com --subject "Report" --attach report.pdf
gog gmail labels list
gog gmail drafts list
```

### Calendar

```bash
gog calendar list                          # today's events
gog calendar list --days 7 --json          # next 7 days, JSON output
gog calendar create --title "Meeting" --start "2025-01-15T10:00:00" --duration 1h
gog calendar delete <eventId>
gog calendar freebusy --emails "a@co.com,b@co.com" --days 3
```

### Drive

```bash
gog drive list
gog drive search "quarterly report"
gog drive upload ./file.pdf
gog drive download <fileId>
gog drive share <fileId> --email user@example.com --role writer
```

### Contacts

```bash
gog contacts search "John"
gog contacts create --name "Jane Doe" --email jane@example.com --phone "+1234567890"
gog contacts update <resourceName> --title "CTO" --company "Acme"
```

### Sheets

```bash
gog sheets read <spreadsheetId> --range "Sheet1!A1:D10" --json
gog sheets write <spreadsheetId> --range "Sheet1!A1" --values '[["Name","Score"],["Alice",95]]'
gog sheets create --title "New Sheet"
```

### Tasks

```bash
gog tasks list
gog tasks add "Buy groceries" --due "2025-01-20"
gog tasks done <taskId>
```

### Chat (Workspace only)

```bash
gog chat spaces list
gog chat send --space <spaceId> --message "Hello team"
```

### Docs & Slides

```bash
gog docs create --title "Meeting Notes"
gog docs export <docId> --format markdown
gog slides create --title "Q4 Presentation"
```

## Output Modes

- Default: human-readable text
- `--json`: structured JSON output for scripting/agents
- `GOG_HELP=full gog --help`: full expanded command list

## Multiple Accounts

```bash
gog auth add work@company.com
gog auth add personal@gmail.com
gog --account work@company.com gmail search "project update"
```

## Agent-Friendly Features

- JSON output with `--json` flag on all commands
- Command allowlist via `GOG_ALLOWED_COMMANDS` for sandboxed/agent runs
- Non-interactive auth flows (`--manual`, `--remote`, `--access-token`)
- Auto-refreshing OAuth tokens
- Structured exit codes
