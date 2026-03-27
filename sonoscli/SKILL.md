---
name: "Sonos CLI (sonoscli)"
description: "CLI to discover and control Sonos speakers over local network — playback, grouping, queue, favorites, scenes, Spotify, and volume. Use when an agent needs to control music playback, manage speaker groups, or play Spotify on Sonos."
---

# sonoscli — Control Sonos speakers from your terminal

Modern Go CLI for Sonos speaker control over your local network (UPnP/SOAP).

- **Repo**: https://github.com/steipete/sonoscli
- **Author**: [@steipete](https://github.com/steipete)

## Installation

```bash
brew install steipete/tap/sonoscli
```

Or build from source:

```bash
go install github.com/steipete/sonoscli/cmd/sonos@latest
```

## Requirements

- Machine must be on the same network as Sonos speakers
- Speakers reachable on TCP port 1400
- Spotify must be linked in Sonos app (for Spotify features)

## Key Commands

### Discovery & Status

```bash
sonos discover
sonos discover --format json
sonos status --name "Kitchen"
sonos now --name "Kitchen"
```

### Playback

```bash
sonos play --name "Kitchen"
sonos pause --name "Kitchen"
sonos stop --name "Kitchen"
sonos next --name "Kitchen"
sonos prev --name "Kitchen"
```

### Volume & Mute

```bash
sonos volume get --name "Kitchen"
sonos volume set --name "Kitchen" 25
sonos mute toggle --name "Kitchen"
```

### Speaker Grouping

```bash
sonos group status
sonos group join --name "Bedroom" --to "Living Room"
sonos group unjoin --name "Bedroom"
sonos group solo --name "Office"
sonos group party --to "Bar"          # all speakers join target
sonos group dissolve --name "Living Room"
```

### Queue Management

```bash
sonos queue list --name "Kitchen"
sonos queue play --name "Kitchen" 1    # play track at position
sonos queue remove --name "Kitchen" 3
sonos queue clear --name "Kitchen"
```

### Favorites

```bash
sonos favorites list --name "Kitchen"
sonos favorites open --name "Kitchen" --index 1
sonos favorites open --name "Kitchen" "BBC Radio 6 Music"
```

### Spotify

```bash
# Play a Spotify link
sonos open --name "Kitchen" https://open.spotify.com/track/6NmXV4o6bmp704aPGyTVVG

# Enqueue a playlist
sonos enqueue --name "Kitchen" spotify:playlist:37i9dQZF1DXcBWIGoYBM5M

# Search and play via SMAPI (no Spotify API credentials needed)
sonos play spotify --name "Office" "gareth emery"

# Search via Spotify Web API (needs SPOTIFY_CLIENT_ID/SECRET)
sonos search spotify --type track "daft punk harder better"
sonos search spotify --open --name "Kitchen" "miles davis so what"
```

### Scenes (Presets)

```bash
sonos scene save "Evening"
sonos scene apply "Evening"
sonos scene list
sonos scene delete "Evening"
```

### Play Arbitrary URI

```bash
sonos play-uri --name "Kitchen" "https://example.com/stream.mp3"
sonos tv --name "Living Room"       # switch to TV input
sonos linein --name "Kitchen" --from "Living Room"
```

### Watch Live Events

```bash
sonos watch --name "Kitchen"
sonos watch --name "Kitchen" --format json
```

## Output Modes

- `--format plain` (default)
- `--format json`
- `--format tsv`
- `--debug` for trace logs

## Configuration

```bash
sonos config set defaultRoom "Office"
sonos config set format json
sonos config get
```

Room targeting supports fuzzy substring matching — `--name "Kit"` matches "Kitchen".
