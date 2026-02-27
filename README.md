# LocalAI Docker Compose

Docker Compose setup for local AI — Ollama with GPU acceleration and Open WebUI.

## Services

- **Ollama** — Local LLM runtime with NVIDIA GPU support, exposed on port `11434`
- **Open WebUI** — Web interface for chatting with Ollama models, exposed on port `3000`

## Requirements

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- NVIDIA GPU with [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html)

## Setup

1. Copy the example env file and set your secret key:

```bash
cp .env.example .env
```

2. Edit `.env` and replace the placeholder value:

```env
WEBUI_SECRET_KEY=your-secret-key-here
```

3. Start the services:

```bash
docker compose up -d
```

Then open http://localhost:3000 in your browser.

## Configuration

Key environment variables:

| Variable | Service | Description |
|---|---|---|
| `OLLAMA_HOST` | ollama | Bind address for the Ollama API |
| `OLLAMA_ORIGINS` | ollama | Allowed CORS origins |
| `OLLAMA_BASE_URL` | open-webui | URL open-webui uses to reach Ollama |
| `WEBUI_SECRET_KEY` | open-webui | Secret key for session signing — set in `.env` |
| `WEBUI_NAME` | open-webui | Display name for the web UI |
| `DEFAULT_LOCALE` | open-webui | Default UI language |
