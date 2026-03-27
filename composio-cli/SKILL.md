---
name: "Composio CLI"
description: "Search, authenticate, and execute tools across 1000+ apps from the terminal. Use when an agent needs to discover available integrations, connect to third-party services, or execute actions across SaaS apps."
---

# Composio CLI

Search, authenticate, and execute tools across 1000+ apps. Type-safe code generation, trigger listeners, and structured JSON output.

- **Docs**: https://docs.composio.dev/docs/cli
- **Website**: https://composio.dev

## Installation

```bash
curl -fsSL https://composio.dev/install | bash
composio login
```

## Key Commands

```bash
composio search "star a github repo"
composio execute GITHUB_STAR_A_REPOSITORY_FOR_THE_AUTHENTICATED_USER -d '{"owner":"composiohq","repo":"composio"}'
composio apps list
composio triggers list
```

## Agent-Friendly Features

- Structured JSON output on all commands
- API key auth via env vars
- Non-interactive execution mode
- 1000+ pre-built tool integrations
