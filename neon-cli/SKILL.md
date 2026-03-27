---
name: "Neon CLI"
description: "Manage Neon serverless Postgres — projects, branches, databases, roles, and connection strings. Use when an agent needs to create database branches, manage Neon projects, or get connection strings for serverless Postgres."
---

# Neon CLI

Manage Neon projects, branches, databases, roles, and connection strings.

- **Docs**: https://neon.com/docs/reference/neon-cli

## Installation

```bash
npm i -g neonctl
neonctl auth
```

## Key Commands

```bash
neonctl projects list
neonctl branches list --project-id <id>
neonctl branches create --project-id <id> --name feature-branch
neonctl databases list --branch <branch-id>
neonctl connection-string --project-id <id>
neonctl roles list --project-id <id>
```

## Agent-Friendly Features

- `--output json` for structured output
- API key auth via `NEON_API_KEY`
- Database branching for preview environments
