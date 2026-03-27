---
name: "ElevenLabs CLI"
description: "Voice and audio service management — text-to-speech, voice cloning, and audio generation. Use when an agent needs to generate speech audio, manage voice models, or work with ElevenLabs audio services."
---

# ElevenLabs CLI

Voice and audio service management from the terminal.

- **Website**: https://elevenlabs.io

## Key Commands

```bash
elevenlabs tts --text "Hello world" --voice "Rachel" --output hello.mp3
elevenlabs voices list
elevenlabs voices clone --name "MyVoice" --files sample1.mp3 sample2.mp3
```

## Agent-Friendly Features

- API key auth via `ELEVENLABS_API_KEY`
- Non-interactive text-to-speech generation
- Voice management from terminal
