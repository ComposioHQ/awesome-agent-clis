---
name: "PostHog CLI"
description: "Query events, manage feature flags, and pull analytics data. Use when an agent needs to query product analytics, toggle feature flags, or pull PostHog event data."
---

# PostHog CLI

Query events, manage feature flags, and pull analytics data.

- **Website**: https://posthog.com

## Key Commands

```bash
posthog events query --event "page_view" --days 7
posthog feature-flags list
posthog feature-flags toggle <flag-key> --enable
```

## Agent-Friendly Features

- API key auth
- JSON output for analytics queries
- Feature flag management
