---
name: "Tavily CLI"
description: "Web search, page extraction, site crawling, and multi-source research from the terminal. Use when an agent needs to search the web, extract content from URLs, crawl sites with an objective, or run deep research across sources."
---

# Tavily CLI

Native web access for agents from the terminal. Search, extract, crawl, and research with structured output designed for agent workflows.

- **Website**: https://tavily.com
- **Docs**: https://docs.tavily.com

## Installation

```bash
curl -fsSL https://cli.tavily.com/install.sh | bash
tvly login
```

## Key Commands

### Search

Natural language web search — results are ranked, filtered, and compressed for LLM use (no raw HTML).

```bash
tvly search "latest developments in AI agents"
tvly search "Series B AI infrastructure companies founded after 2023" --json
```

### Extract

Pull structured content from a specific URL.

```bash
tvly extract "https://docs.example.com/api" --json
```

### Crawl

Crawl a site with a specific objective.

```bash
tvly crawl "https://docs.tavily.com/welcome" --objective "find documentation on n8n integration" --json
```

### Research

Deep multi-source research on a topic.

```bash
tvly research "competitive landscape of AI code assistants" --json
```

## Output Modes

- Default: human-readable
- `--json`: structured JSON output for agent parsing

## Agent-Friendly Features

- All commands support `--json` for structured output
- Results pre-processed for LLM consumption (no raw HTML cleanup needed)
- Designed for iterative search loops (search → inspect → refine → search again)
- API key auth via `tvly login`
