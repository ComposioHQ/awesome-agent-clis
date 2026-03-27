---
name: "Google Workspace CLI (gws)"
description: "One CLI for all of Google Workspace — Drive, Gmail, Calendar, Sheets, Docs, Chat, Admin, and more. Dynamically built from Google's Discovery Service. Use when an agent needs broad Google Workspace access with 100+ built-in agent skills."
---

# Google Workspace CLI (gws)

One CLI for all of Google Workspace. Dynamically built from Google's Discovery Service — when Google adds an API endpoint, `gws` picks it up automatically.

- **Repo**: https://github.com/googleworkspace/cli

## Key Features

- Drive, Gmail, Calendar, Sheets, Docs, Chat, Admin, and more
- 100+ agent skills included
- Structured JSON output
- Structured exit codes (0–5)
- Helper commands: `+send`, `+agenda`, `+triage`
- Model Armor response sanitization

## Key Commands

```bash
gws +agenda                     # today's calendar
gws +send --to user@example.com --subject "Hello" --body "Hi"
gws +triage                     # inbox triage
gws gmail.users.messages.list --userId me --format json
gws calendar.events.list --calendarId primary --format json
gws drive.files.list --format json
```

## Agent-Friendly Features

- JSON output on all commands
- 100+ pre-built agent skills
- Exit codes 0–5 for structured error handling
- Model Armor for response sanitization
- Auto-discovers new Google API endpoints
