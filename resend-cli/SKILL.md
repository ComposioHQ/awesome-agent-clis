---
name: "Resend CLI"
description: "Send emails, manage domains, API keys, contacts, and broadcasts. Use when an agent needs to send transactional or marketing emails, manage email contacts, or configure email domains."
---

# Resend CLI

Send emails, manage domains, API keys, contacts, and broadcasts. 53 commands across 13 resources.

- **Repo**: https://github.com/resend/resend-cli
- **Author**: [@zenorocha](https://github.com/zenorocha)

## Installation

```bash
npm i -g resend
resend login
```

## Key Commands

```bash
resend emails send --from "you@example.com" --to "them@example.com" --subject "Hello" --text "Hi there"
resend domains list
resend contacts list --audience-id <id>
resend api-keys list
resend broadcasts list
```

## Agent-Friendly Features

- Auto-detects TTY — outputs JSON when piped
- Natural language scheduling
- Idempotency keys for safe retries
- `resend doctor` for agent environment detection
- 53 commands across 13 resources
- Meaningful exit codes
