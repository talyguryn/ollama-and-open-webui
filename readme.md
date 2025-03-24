![](./assets/banner.png)

# Ollama + Open WebUI

Sample docker-compose file for running [Ollama](https://ollama.com) and [Open WebUI](https://openwebui.com).

The idea is to set up and run both services in one command without using command line tools.

## Requirements

Make sure you have installed [Docker](https://docs.docker.com/get-docker/) with Docker Compose.

Check the free space on your disk, because uncomressed images are heavy:

- Ollama: ~4GB
- Open WebUI: ~4GB

Also you need to have a space for local models.

Check required RAM for models individually.

## Usage

Add env configs to docker-compose.yml file if it is needed.

Then run contaners with:

```bash
docker compose up -d
```

### Add models in config

You can add more models to entrypoint command in `ollama` service in `docker-compose.yml` file.

Example: add `ollama pull llama3.2:3b &&` command to the chain to download llama3.2:3b.

Final command:

`ollama serve & sleep 5 && ollama pull deepseek-r1:1.5b && ollama pull llama3.2:3b && wait`

## Env vars lists

Configure more params in docker-compose config via env vars for containers:

- [Ollama ENV](https://github.com/ollama/ollama/issues/2941#issuecomment-2322778733)
- [Open WebUI ENV](https://docs.openwebui.com/getting-started/env-configuration#overview)
