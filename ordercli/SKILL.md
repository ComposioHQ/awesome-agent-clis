---
name: "Food Delivery CLI (ordercli)"
description: "CLI for Foodora and Deliveroo — view order history, track active orders, and reorder past meals. Use when an agent needs to check food delivery order status, review past orders, or reorder from Foodora/Deliveroo."
---

# ordercli — Your takeout timeline, in the terminal

CLI for Foodora and Deliveroo food delivery services.

- **Repo**: https://github.com/steipete/ordercli
- **Author**: [@steipete](https://github.com/steipete)

## Installation

Build from source:

```bash
git clone https://github.com/steipete/ordercli.git
cd ordercli
go build ./cmd/ordercli
```

## Supported Providers

- **Foodora** — fully working
- **Deliveroo** — work in progress (requires bearer token)

## Foodora Setup

### Configure Country

```bash
ordercli foodora countries              # list available countries
ordercli foodora config set --country AT
ordercli foodora config show
```

### Login

```bash
ordercli foodora login --email you@example.com --password-stdin
```

If MFA triggers, it prompts for OTP automatically in a TTY.

For regions with Cloudflare protection:

```bash
ordercli foodora login --email you@example.com --password-stdin --browser
```

### Import Session from Chrome

```bash
ordercli foodora session chrome --url https://www.foodora.at/ --profile "Default"
ordercli foodora session refresh --client-id android
```

## Key Commands

### Order History

```bash
ordercli foodora history
ordercli foodora history --limit 50
ordercli foodora history show <orderCode>
ordercli foodora history show <orderCode> --json
```

### Active Orders

```bash
ordercli foodora orders
ordercli foodora orders --watch
```

### Reorder

```bash
# Preview only (safe)
ordercli foodora reorder <orderCode>

# Actually add to cart (does NOT place order)
ordercli foodora reorder <orderCode> --confirm

# With specific delivery address
ordercli foodora reorder <orderCode> --confirm --address-id <id>
```

### Logout

```bash
ordercli foodora logout
```

## Deliveroo (WIP)

```bash
export DELIVEROO_BEARER_TOKEN='...'
ordercli deliveroo config set --market uk
ordercli deliveroo history
ordercli deliveroo orders
```

## Configuration

Config stored in OS config dir. Override with:

```bash
ordercli --config /tmp/ordercli.json foodora config show
```
