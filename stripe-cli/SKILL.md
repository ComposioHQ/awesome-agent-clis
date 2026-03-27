---
name: "Stripe CLI"
description: "Test webhooks, trigger events, tail API logs, and manage Stripe resources. Use when an agent needs to test Stripe integrations, listen for webhook events, or inspect Stripe API activity."
---

# Stripe CLI

Test webhooks, trigger events, tail API logs, and manage Stripe resources from the terminal.

- **Repo**: https://github.com/stripe/stripe-cli
- **Docs**: https://stripe.com/docs/stripe-cli

## Installation

```bash
brew install stripe/stripe-cli/stripe
stripe login
```

## Key Commands

```bash
stripe listen --forward-to localhost:4242/webhook
stripe trigger payment_intent.succeeded
stripe logs tail
stripe resources list
stripe customers list --json
stripe payments list --limit 5 --json
```

## Agent-Friendly Features

- `--json` flag for structured output
- API key auth via `STRIPE_API_KEY`
- Non-interactive webhook forwarding
- Event triggering for testing
