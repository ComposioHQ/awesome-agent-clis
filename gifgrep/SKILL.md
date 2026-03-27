---
name: "GIF Search CLI (gifgrep)"
description: "Search GIFs from Tenor and Giphy via CLI or TUI, download GIFs, and extract stills or sprite sheets. Use when an agent needs to find a GIF by keyword, download it, or generate a still frame or contact sheet from a GIF."
---

# gifgrep — Grep the GIF

Search GIF providers (Tenor, Giphy) with scriptable CLI output or interactive TUI with inline previews.

- **Repo**: https://github.com/steipete/gifgrep
- **Website**: https://gifgrep.com
- **Author**: [@steipete](https://github.com/steipete)

## Installation

```bash
brew install steipete/tap/gifgrep
```

Or via Go:

```bash
go install github.com/steipete/gifgrep/cmd/gifgrep@latest
```

## Key Commands

### Search GIFs

```bash
gifgrep cats --max 5
gifgrep cats --format url | head -n 5
gifgrep cats --json | jq '.[0].url'
gifgrep "office handshake" --source giphy --max 3 --json
```

### Download

```bash
gifgrep cats --download --max 1 --format url
gifgrep cats --download --reveal    # download and reveal in Finder
```

### Extract Stills & Sheets

```bash
gifgrep still ./clip.gif --at 1.5s -o still.png
gifgrep sheet ./clip.gif --frames 9 --cols 3 -o sheet.png
```

### Interactive TUI

```bash
gifgrep tui "office handshake"
```

## Providers

Select via `--source`:

- `auto` (default): prefers Giphy when `GIPHY_API_KEY` is set, else Tenor
- `tenor`: uses public demo key if `TENOR_API_KEY` is unset
- `giphy`: requires `GIPHY_API_KEY`

## Output Modes

- Default: human-readable (TTY-aware)
- `--json`: array of objects with `id`, `title`, `url`, `preview_url`, `tags`, `width`, `height`
- `--format url`: one URL per line (pipeable)
- `--thumbs`: inline still-frame thumbnails (Kitty/iTerm2 terminals)

## Environment Variables

- `TENOR_API_KEY` (optional)
- `GIPHY_API_KEY` (required for `--source giphy`)
