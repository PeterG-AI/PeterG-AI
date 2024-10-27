# Peter

<img src="./docs/peter_banner.jpg" alt="Peter Banner" width="100%">

*As seen powering Peter G-AI*

- *Multi-Agent Simulation:* Easily manage multiple unique characters.
- *Integrated Connectors:* Supports Discord and Twitter, including voice channel functionality.
- *Conversational Memory:* Retains context and documents for richer interactions.
- *Content Processing:* Reads links, PDFs, transcribes audio/video, and summarizes discussions.
- *Extensible Framework:* Create custom actions and clients to enhance functionality.
- *Local and Open-Source Model Support:* Pre-configured with Nous Hermes Llama 3.1B.
- *Cloud Inference:* Utilize OpenAI for efficient processing.
- *Complex Query Assistance:* Use "Ask Claude" mode for advanced responses.
- *Ask Claude:* mode for calling Claude on more complex queries
- *Built with TypeScript:* Ensures high performance and maintainability.

# Getting Started

## Install Node.js
https://docs.npmjs.com/downloading-and-installing-node-js-and-npm

## Edit the .env file
- Copy .env.example to .env and fill in the appropriate values
- Edit the TWITTER environment variables to add your bot's username and password

## Edit the character file
- Check out the file `src/core/defaultCharacter.ts` - you can modify this
- You can also load characters with the `node --loader ts-node/esm src/index.ts --characters="path/to/your/character.json"` and run multiple bots at the same time.

### Linux Installation
You might need these
```
npm install --include=optional sharp
```

### Run with Llama
You can run Llama 70B or 405B models by setting the `XAI_MODEL` environment variable to `meta-llama/Meta-Llama-3.1-70B-Instruct-Turbo` or `meta-llama/Meta-Llama-3.1-405B-Instruct`

### Run with Grok
You can run Grok models by setting the `XAI_MODEL` environment variable to `grok-beta`

### Run with OpenAI
You can run OpenAI models by setting the `XAI_MODEL` environment variable to `gpt-4o-mini` or `gpt-4o`

# Requires Node 20+
If you are getting strange issues when starting up, make sure you're using Node 20+. Some APIs are not compatible with previous versions. You can check your node version with `node -v`. If you need to install a new version of node, we recommend using [nvm](https://github.com/nvm-sh/nvm).

## Additional Requirements
You may need to install Sharp. If you see an error when starting up, try installing it with the following command:
```
npm install --include=optional sharp
```

# Environment Setup

You will need to add environment variables to your .env file to connect to various platforms:
```
# Required environment variables
# Start Discord
DISCORD_APPLICATION_ID=
DISCORD_API_TOKEN= # Bot token

# Start Twitter
TWITTER_USERNAME= # Account username
TWITTER_PASSWORD= # Account password
TWITTER_EMAIL= # Account email
TWITTER_COOKIES= # Account cookies
```

# Local Setup

## CUDA Setup

If you have an NVIDIA GPU, you can install CUDA to speed up local inference dramatically.
```
npm install
npx --no node-llama-cpp download --gpu cuda
```

Make sure that you've installed the CUDA Toolkit, including cuDNN and cuBLAS.

# Cloud Setup (with OpenAI)

In addition to the environment variables above, you will need to add the following:
```
# OpenAI handles the bulk of the work with chat, TTS, image recognition, etc.
OPENAI_API_KEY=sk-* # OpenAI API key, starting with sk-

# The agent can also ask Claude for help if you have an API key
ANTHROPIC_API_KEY=

# For Elevenlabs voice generation on Discord voice
ELEVENLABS_XI_API_KEY= # API key from elevenlabs

# ELEVENLABS SETINGS
ELEVENLABS_MODEL_ID=eleven_multilingual_v2
ELEVENLABS_VOICE_ID=21m00Tcm4TlvDq8ikWAM
ELEVENLABS_VOICE_STABILITY=0.5
ELEVENLABS_VOICE_SIMILARITY_BOOST=0.9
ELEVENLABS_VOICE_STYLE=0.66
ELEVENLABS_VOICE_USE_SPEAKER_BOOST=false
ELEVENLABS_OPTIMIZE_STREAMING_LATENCY=4
ELEVENLABS_OUTPUT_FORMAT=pcm_16000
```

# Discord Bot
For help with setting up your Discord Bot, check out here: https://discordjs.guide/preparations/setting-up-a-bot-application.html
