---
name: "PlanetScale CLI (pscale)"
description: "Branch, deploy, and manage MySQL databases with deploy requests. Use when an agent needs to manage PlanetScale databases, create branches, or submit deploy requests for schema changes."
---

# PlanetScale CLI (pscale)

Branch, deploy, and manage MySQL databases with deploy requests.

- **Repo**: https://github.com/planetscale/cli
- **Docs**: https://planetscale.com/docs/reference/planetscale-cli

## Installation

```bash
brew install planetscale/tap/pscale
pscale auth login
```

## Key Commands

```bash
pscale database list --json
pscale branch list <database> --json
pscale branch create <database> feature-branch
pscale deploy-request create <database> feature-branch
pscale deploy-request deploy <database> <number>
pscale shell <database> <branch>
pscale connect <database> <branch> --port 3306
```

## Agent-Friendly Features

- `--json` for structured output
- Service token auth for CI/CD
- Non-interactive deploy requests
- Database branching workflow
