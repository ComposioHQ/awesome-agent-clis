---
name: "Sentry CLI"
description: "Manage Sentry releases, upload debug symbols and source maps, send events, monitor crons, and stream logs. Use when an agent needs to create releases, upload source maps, manage debug info files, or send test events to Sentry."
---

# Sentry CLI

Official CLI for Sentry. Manages releases, debug information files, source maps, cron monitors, logs, and event sending. Used in CI/CD pipelines and build processes.

- **Repo**: https://github.com/getsentry/sentry-cli
- **Docs**: https://docs.sentry.io/cli/
- **Compatibility**: Sentry SaaS and Self-Hosted 24.11.1+

## Installation

```bash
# npm
npm i -g @sentry/cli

# curl
curl -sL https://sentry.io/get-cli/ | bash

# Homebrew
brew install getsentry/tools/sentry-cli

# Docker
docker run --rm -v $(pwd):/work getsentry/sentry-cli --help
```

## Configuration

```bash
# Interactive login
sentry-cli login

# Or set env vars
export SENTRY_AUTH_TOKEN=<token>
export SENTRY_ORG=<org-slug>
export SENTRY_PROJECT=<project-slug>
```

Config can also live in `.sentryclirc` or `~/.sentryclirc`.

## Key Commands

### Release Management

```bash
sentry-cli releases list --format json
sentry-cli releases new <version>
sentry-cli releases set-commits <version> --auto
sentry-cli releases files <version> upload-sourcemaps ./dist
sentry-cli releases finalize <version>
sentry-cli releases deploys <version> new -e production
```

### Debug Information Files

```bash
sentry-cli debug-files check <path>
sentry-cli debug-files upload <path>
sentry-cli debug-files list
```

### Send Events

```bash
sentry-cli send-event -m "Test event"
sentry-cli send-event -m "Error occurred" -l error --logfile /var/log/app.log
```

### Logs

```bash
sentry-cli logs list
sentry-cli logs stream
```

### Cron Monitors

```bash
sentry-cli monitors list
sentry-cli monitors run <monitor-slug> -- <command>
```

## Agent-Friendly Features

- `--format json` for structured output
- Auth via `SENTRY_AUTH_TOKEN`, `SENTRY_ORG`, `SENTRY_PROJECT` env vars
- Non-interactive release and deploy management
- Source map and debug symbol upload for CI/CD
- Cron wrapping with `monitors run`

## See Also

For interactive issue management, AI-powered root cause analysis, and natural language commands, see the new [Sentry developer CLI](https://cli.sentry.dev/) (`sentry` command — separate from `sentry-cli`).
