---
name: "GitHub CLI (gh)"
description: "Manage GitHub issues, PRs, repos, actions, and code search from the terminal. Use when an agent needs to create issues, open pull requests, manage releases, or search code on GitHub."
---

# GitHub CLI (gh)

Issues, PRs, repos, actions, and code search from the terminal.

- **Repo**: https://github.com/cli/cli
- **Docs**: https://cli.github.com/manual/

## Installation

```bash
brew install gh
gh auth login
```

## Key Commands

```bash
gh issue list --json number,title,state
gh issue create --title "Bug" --body "Description"
gh pr list --json number,title,headRefName
gh pr create --title "Feature" --body "Description"
gh pr merge <number> --squash
gh repo clone owner/repo
gh repo create my-repo --public
gh run list --json status,name,conclusion
gh api repos/owner/repo/releases --jq '.[0].tag_name'
gh search code "function_name" --json path,repository
```

## Agent-Friendly Features

- `--json` with `--jq` for precise field extraction
- `gh api` for arbitrary GitHub API calls
- Token auth via `GH_TOKEN` or `GITHUB_TOKEN`
- Non-interactive mode for all commands
- Structured exit codes
