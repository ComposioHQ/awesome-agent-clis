---
name: "DeployHQ CLI"
description: "Deploy code, manage servers, and automate release workflows on DeployHQ. Use when an agent needs to trigger deployments, check deployment status, roll back releases, or manage project configurations."
---

# DeployHQ CLI

Deploy code, manage servers, projects, and automate release workflows on DeployHQ from the terminal.

- **Repo**: https://github.com/deployhq/deployhq-cli
- **Docs**: https://www.deployhq.com/support

## Installation

```bash
# macOS / Linux
brew install deployhq/tap/dhq

# Or via script
curl -fsSL https://raw.githubusercontent.com/deployhq/deployhq-cli/main/install.sh | sh

# Authenticate (non-interactive for agents)
export DEPLOYHQ_ACCOUNT=myaccount
export DEPLOYHQ_EMAIL=me@example.com
export DEPLOYHQ_API_KEY=abc123
```

## Key Commands

```bash
# List projects
dhq projects list --json identifier,name

# Deploy latest commit
dhq deploy -p my-app -s production --use-latest --json

# Check deployment status
dhq deployments show <id> -p my-app --json status,timestamps

# View logs
dhq deployments logs <id> -p my-app

# Rollback
dhq rollback <id> -p my-app --json

# Escape hatch — any API endpoint
dhq api GET /projects/<id>/environment_variables
```

## Agent-Friendly Features

- **`--json <fields>` field selection** — request only the fields you need, e.g. `--json identifier,status`
- **Piped output auto-detection** — automatically switches to JSON when stdout is piped
- **Agent detection** — set `DEPLOYHQ_AGENT=1` to enable agent mode (also detects `CLAUDE_CODE` and `CI`)
- **Breadcrumbs** — JSON responses include a `breadcrumbs` array with suggested next commands
- **JSONL capture** — set `DEPLOYHQ_OUTPUT_FILE=log.jsonl` to record every command's output
- **Meaningful exit codes** — 0 for success, 1 for failure, with structured error details in JSON
- **Non-interactive auth** — three env vars, no browser or prompt required
