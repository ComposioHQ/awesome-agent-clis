---
name: "Sentry CLI"
description: "Manage releases, upload source maps, and query issues in Sentry. Use when an agent needs to create Sentry releases, upload debug artifacts, or query error tracking data."
---

# Sentry CLI

Manage releases, upload source maps, and query issues.

- **Repo**: https://github.com/getsentry/sentry-cli
- **Docs**: https://docs.sentry.io/cli/

## Installation

```bash
npm i -g @sentry/cli
```

## Key Commands

```bash
sentry-cli releases list --format json
sentry-cli releases new <version>
sentry-cli releases files <version> upload-sourcemaps ./dist
sentry-cli releases finalize <version>
sentry-cli issues list --format json
sentry-cli send-event -m "Test event"
```

## Agent-Friendly Features

- `--format json` for structured output
- Auth via `SENTRY_AUTH_TOKEN` and `SENTRY_ORG` / `SENTRY_PROJECT`
- Non-interactive release management
- Source map upload for deployments
