---
name: "Notion CLI (ntn)"
description: "CLI for Notion — authenticate, manage Workers, interact with the Notion API, and upload files. Use when an agent needs to create or query Notion pages, manage databases, upload files to Notion, or deploy Notion Workers."
---

# ntn — The Notion CLI

Official Notion CLI for authentication, Workers management, and API access.

- **Package**: https://www.npmjs.com/package/ntn
- **Author**: Notion ([@makenotion](https://github.com/makenotion))

## Installation

```bash
npm i -g ntn
```

## Authentication

```bash
ntn login
ntn logout
```

## Key Commands

### Notion API

Access the full public Notion API from the terminal. Requires a Notion integration token via `NOTION_API_TOKEN`.

```bash
# List available API endpoints
ntn api ls

# View endpoint spec or docs
ntn api v1/pages --spec -X POST
ntn api v1/pages --docs -X POST

# Create a page
ntn api v1/pages parent[page_id]=abc123

# Query with typed JSON
ntn api v1/pages archived:=true properties[count]:=10

# Query params and headers
ntn api v1/users page_size==100 Accept:application/json
```

### Inline Request Syntax

```bash
# Direct JSON body
ntn api v1/pages -d '{"parent":{"page_id":"abc123"}}'

# String assignment
ntn api v1/pages parent[page_id]=abc123

# Typed JSON assignment
ntn api v1/pages archived:=true properties[count]:=10

# Query params
ntn api v1/users page_size==100

# Headers
ntn api v1/users Accept:application/json
```

Method selection:
- `GET` by default
- `POST` automatically when body fields are present
- `-X/--method` overrides

### File Uploads

```bash
# Upload a file from stdin
ntn files create < file.png

# Upload from URL
ntn files create --external-url https://example.com/photo.png

# List and inspect uploads
ntn files list
ntn files get <upload-id>
```

### Workers

```bash
ntn workers --help
ntn workers list
ntn workers deploy
```

## Environment Variables

- `NOTION_API_TOKEN`: Notion integration token (required for `ntn api` and `ntn files` commands)

## Notes

- `ntn files create` is intentionally quiet on success — shows a progress bar only when stderr is a TTY
- Shell completion can suggest API paths and supported methods
- Currently in alpha — focused on Workers development workflows
