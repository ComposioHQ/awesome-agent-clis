---
name: "Remotion CLI"
description: "Render videos, audio, and still images programmatically with React using terminal commands. Use when an agent needs to preview compositions, list available compositions, or render media artifacts from a Remotion project."
---

# Remotion CLI

Official CLI for Remotion, a React-based framework for making videos programmatically.

- **Repo**: https://github.com/remotion-dev/remotion
- **Docs**: https://www.remotion.dev/docs/cli/

## Installation

```bash
# Run without installing globally
npx remotion --help

# Or install in a project
npm install remotion
```

Most usage is via `npx remotion ...` inside a Remotion project.

## Key Commands

```bash
# Start the Remotion Studio preview UI
npx remotion studio

# List available composition IDs
npx remotion compositions

# Render a composition to a file
npx remotion render <composition-id> out/video.mp4

# Create a bundle for rendering workflows
npx remotion bundle
```

## Agent-Friendly Features

- Scriptable CLI entrypoint via `npx remotion`
- Non-interactive rendering with explicit composition IDs and output paths
- Supports video, audio, and still rendering workflows
- Pass composition props and render settings through flags
- Useful for agents generating marketing videos, demos, explainers, and visual assets from code

## Notes

- `studio` is useful for previewing and iterating locally
- `render` is the main command for automated media generation
- `compositions` helps agents discover which composition IDs exist before rendering
- Rendering works best when the project is already set up with Remotion compositions
