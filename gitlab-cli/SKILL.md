---
name: "GitLab CLI (glab)"
description: "Manage GitLab merge requests, issues, pipelines, and CI/CD from the terminal. Use when an agent needs to create MRs, manage issues, or monitor CI/CD pipelines on GitLab."
---

# GitLab CLI (glab)

MRs, issues, pipelines, and CI/CD management from the terminal.

- **Repo**: https://gitlab.com/gitlab-org/cli
- **Docs**: https://docs.gitlab.com/ee/editor_extensions/gitlab_cli/

## Installation

```bash
brew install glab
glab auth login
```

## Key Commands

```bash
glab mr list --output json
glab mr create --title "Feature" --description "Details"
glab issue list --output json
glab issue create --title "Bug" --description "Details"
glab ci list
glab ci view <pipeline-id>
glab repo clone owner/repo
```

## Agent-Friendly Features

- `--output json` for structured output
- Token auth via `GITLAB_TOKEN`
- Non-interactive CI/CD management
