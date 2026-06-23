# @runapi.ai/elevenlabs-mcp

RunAPI MCP server for the **ElevenLabs** model line. Create tasks,
poll their status, and check pricing through a single RunAPI API key.

## Tools

- `isolate_audio` — create a ElevenLabs task (isolate audio) and (optionally) poll until it reaches a terminal status. Returns the task id, status, output URLs, and a price snapshot. Models: `audio-isolation`, `speech-to-text`, `text-to-dialogue-v3`, `sound-effect-v2`, `text-to-speech-multilingual-v2`, `text-to-speech-turbo-v2.5`.
- `speech_to_text` — create a ElevenLabs task (speech to text) and (optionally) poll until it reaches a terminal status. Returns the task id, status, output URLs, and a price snapshot. Models: `audio-isolation`, `speech-to-text`, `text-to-dialogue-v3`, `sound-effect-v2`, `text-to-speech-multilingual-v2`, `text-to-speech-turbo-v2.5`.
- `text_to_dialogue` — create a ElevenLabs task (text to dialogue) and (optionally) poll until it reaches a terminal status. Returns the task id, status, output URLs, and a price snapshot. Models: `audio-isolation`, `speech-to-text`, `text-to-dialogue-v3`, `sound-effect-v2`, `text-to-speech-multilingual-v2`, `text-to-speech-turbo-v2.5`.
- `text_to_sound` — create a ElevenLabs task (text to sound) and (optionally) poll until it reaches a terminal status. Returns the task id, status, output URLs, and a price snapshot. Models: `audio-isolation`, `speech-to-text`, `text-to-dialogue-v3`, `sound-effect-v2`, `text-to-speech-multilingual-v2`, `text-to-speech-turbo-v2.5`.
- `text_to_speech` — create a ElevenLabs task (text to speech) and (optionally) poll until it reaches a terminal status. Returns the task id, status, output URLs, and a price snapshot. Models: `audio-isolation`, `speech-to-text`, `text-to-dialogue-v3`, `sound-effect-v2`, `text-to-speech-multilingual-v2`, `text-to-speech-turbo-v2.5`.
- `get_task` — fetch the current status and latest payload for a task.
- `check_pricing` — look up pricing for a model in this line.

## Configuration

Set a RunAPI API key via the `RUNAPI_API_KEY` environment variable, or write
it to `~/.config/runapi/config.json`:

```bash
mkdir -p ~/.config/runapi
echo '{"api_key":"YOUR_KEY"}' > ~/.config/runapi/config.json
```

Get an API key at https://runapi.ai. Pricing is listed at
https://runapi.ai/pricing.

## Usage

Run the server over stdio:

```bash
npx -y @runapi.ai/elevenlabs-mcp
```

Add it to an MCP client (see `examples/` for per-client configs):

```json
{
  "mcpServers": {
    "elevenlabs": {
      "command": "npx",
      "args": ["-y", "@runapi.ai/elevenlabs-mcp"],
      "env": { "RUNAPI_API_KEY": "${RUNAPI_API_KEY}" }
    }
  }
}
```

## License

Apache-2.0
