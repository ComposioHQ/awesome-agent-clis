---
name: "Turso CLI"
description: "Manage libSQL/SQLite databases, replicas, and groups. Use when an agent needs to create or manage Turso databases, configure replicas, or get database connection URLs."
---

# Turso CLI

Manage libSQL/SQLite databases, replicas, and groups.

- **Repo**: https://github.com/tursodatabase/turso-cli
- **Docs**: https://docs.turso.tech/cli

## Installation

```bash
brew install tursodatabase/tap/turso
turso auth login
```

## Key Commands

```bash
turso db list
turso db create my-database
turso db show my-database
turso db tokens create my-database
turso db shell my-database
turso group list
turso group create my-group --location ord
```

## Agent-Friendly Features

- Token auth via `TURSO_API_TOKEN`
- `--json` output on list commands
- Non-interactive database provisioning
