---
name: "WhatsApp CLI (wacli)"
description: "CLI for WhatsApp messaging — sync history, search messages, send texts and files, manage contacts and groups. Use when an agent needs to send WhatsApp messages, search chat history, or manage WhatsApp groups."
---

# wacli — WhatsApp CLI

Sync, search, and send WhatsApp messages from the terminal. Built on `whatsmeow` (WhatsApp Web protocol).

- **Repo**: https://github.com/steipete/wacli
- **Author**: [@steipete](https://github.com/steipete)

## Installation

```bash
brew install steipete/tap/wacli
```

Or build from source:

```bash
go build -tags sqlite_fts5 -o ./dist/wacli ./cmd/wacli
```

## Authentication

```bash
# Shows QR code — scan with WhatsApp on your phone
wacli auth

# Start continuous sync (must be authenticated first)
wacli sync --follow
```

Default store directory: `~/.wacli` (override with `--store DIR`).

## Key Commands

### Send Messages

```bash
# Send a text message
wacli send text --to 1234567890 --message "hello"

# Send a file with caption
wacli send file --to 1234567890 --file ./photo.jpg --caption "Check this out"

# Send a file with custom display name
wacli send file --to 1234567890 --file /tmp/abc123 --filename report.pdf
```

### Search Messages

```bash
wacli messages search "meeting"
wacli messages search "project update" --json
```

### Groups

```bash
wacli groups list
wacli groups rename --jid 123456789@g.us --name "New Group Name"
```

### History Backfill

```bash
# Backfill older messages for a chat (requires primary device online)
wacli history backfill --chat 1234567890@s.whatsapp.net --requests 10 --count 50
```

### Media

```bash
wacli media download --chat 1234567890@s.whatsapp.net --id <message-id>
```

### Diagnostics

```bash
wacli doctor
```

## Output Modes

- Default: human-readable
- `--json`: structured JSON output for agents

## Environment Variables

- `WACLI_DEVICE_LABEL`: set linked device label shown in WhatsApp
- `WACLI_DEVICE_PLATFORM`: override linked device platform (defaults to `CHROME`)
