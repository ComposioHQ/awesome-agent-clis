---
name: "Stripe Projects CLI"
description: "Provision provider-backed services, link accounts, sync credentials, and manage billing from the terminal. Use when an agent needs to set up Stripe-powered services, manage project credentials, or handle service provisioning."
---

# Stripe Projects CLI

Provision provider-backed services from the terminal, link existing accounts, sync credentials into `.env`, and manage upgrades and billing.

- **Docs**: https://docs.stripe.com/projects

## Key Commands

```bash
stripe projects init
stripe projects link
stripe projects sync
stripe projects upgrade
```

## Agent-Friendly Features

- `--json` for structured output
- `--no-interactive` for non-interactive mode
- `--auto-confirm` to skip confirmation prompts
- Credential sync to `.env` files
