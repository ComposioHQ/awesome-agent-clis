---
name: "Vercel CLI"
description: "Deploy projects, manage domains, env vars, and inspect logs on Vercel. Use when an agent needs to deploy a web app, configure environment variables, or manage Vercel project settings."
---

# Vercel CLI

Deploy projects, manage domains and env vars, inspect logs, and sync local project settings.

- **Repo**: https://github.com/vercel/vercel
- **Docs**: https://vercel.com/docs/cli

## Installation

```bash
npm i -g vercel
vercel login
```

## Key Commands

```bash
vercel deploy
vercel deploy --prod
vercel env ls
vercel env add VARIABLE_NAME production
vercel domains ls
vercel logs <deployment-url>
vercel pull                    # sync project settings locally
vercel inspect <deployment-url>
```

## Agent-Friendly Features

- Token auth via `--token` or `VERCEL_TOKEN` for CI
- `--yes` flag to skip confirmation prompts
- JSON output on inspection commands
- Non-interactive deployment mode
