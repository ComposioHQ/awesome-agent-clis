---
name: "CodeRabbit CLI"
description: "Review local code changes before commit, surface bugs and security issues, and feed findings back into an AI coding loop. Use when an agent needs to run terminal-native code review on a Git repo and act on the results."
---

# CodeRabbit CLI

AI code reviews directly in the terminal before commit. Reviews uncommitted changes, supports agent-friendly output modes, and integrates well with coding-agent fix loops.

- **Docs**: https://docs.coderabbit.ai/cli/overview
- **Docs Index**: https://docs.coderabbit.ai/llms.txt
- **Status**: Open beta

## Installation

```bash
# Install script
curl -fsSL https://cli.coderabbit.ai/install.sh | sh

# Homebrew
brew install coderabbit
```

The CLI binary is `coderabbit`, with `cr` as a short alias.

## Authentication

```bash
# Browser-based login
cr auth login

# API key login
coderabbit auth login --api-key "cr-************"
```

CodeRabbit links the CLI to your account so reviews can use plan limits, team learnings, and codebase context where available.

## Key Commands

```bash
# Review current repo changes
cr

# Plain text output
cr --plain

# Minimal output for AI coding agents
cr --prompt-only

# Review against a non-main base branch
cr --base develop

# Explicitly review uncommitted changes
cr --prompt-only --type uncommitted
```

The CLI must be run from inside a Git repository.

## Agent-Friendly Features

- `cr --prompt-only` for minimal agent-oriented output
- `--plain` for detailed terminal review output without the full interactive UI
- Works well in background review/fix loops for coding agents
- Reviews local, uncommitted changes before code reaches a PR
- Can apply simple suggested fixes directly from the interactive interface
- Native guidance for Claude Code and Codex workflows in the docs

## Suggested Agent Workflow

```text
Implement the task, then run cr --prompt-only --type uncommitted in the background.
Fix major issues only. Run one final pass after the fixes and stop after two loops.
```

Use CodeRabbit to detect issues, then use the coding agent to implement the fixes. This is especially useful for race conditions, memory leaks, logic bugs, and security findings that are easier to address before commit.
