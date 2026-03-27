---
name: "Railway CLI"
description: "Deploy services, manage variables, and provision databases on Railway. Use when an agent needs to deploy backend services, manage environment variables, or provision databases on Railway."
---

# Railway CLI

Deploy services, manage variables, and provision databases from the terminal.

- **Repo**: https://github.com/railwayapp/cli
- **Docs**: https://docs.railway.com/guides/cli

## Installation

```bash
brew install railway
railway login
```

## Key Commands

```bash
railway init
railway up                     # deploy
railway variables list
railway variables set KEY=value
railway logs
railway status
railway link                   # link to existing project
railway add                    # provision a database
```

## Agent-Friendly Features

- Token auth via `RAILWAY_TOKEN`
- Non-interactive deployments
- Database provisioning from CLI
