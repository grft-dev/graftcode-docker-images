# graftcode-docker-images

`graftcode-docker-images` is a public repository of Dockerfiles for official GraftCode Gateway container images.

## Overview

This repository provides source Dockerfiles for official Docker Hub images that include GraftCode Gateway preinstalled. Each image downloads the latest `gg_linux_amd64.deb` installer from the `graftcode-gateway` GitHub Releases.

## Images in this repo

| Image | Base image | Docker Hub repository | Tags |
|---|---|---|---|
| Java | `eclipse-temurin:21-jdk` | `graftcode/eclipse-temurin` | `21-jdk` |
| .NET | `mcr.microsoft.com/dotnet/sdk:10.0` | `graftcode/netcore` | `10.0-latest`, `10.0` |
| Node.js | `node:22` | `graftcode/node` | `22` |
| Python | `python:3.12-slim` | `graftcode/python` | `3.12` |

## Pull official images

Use the public Docker Hub repositories and tags below:

```bash
docker pull graftcode/eclipse-temurin:21-jdk
docker pull graftcode/netcore:10.0-latest
docker pull graftcode/node:22
docker pull graftcode/python:3.12
```

## Run an image

Example:

```bash
docker run --rm -p 80:80 graftcode/eclipse-temurin:21-jdk
```

## Image purpose

Each image is built to run the `gg` binary from GraftCode Gateway and expose port `80` by default. This repository is intended as the public source for these Docker image definitions.

## OCI metadata

All images include standard OCI labels:

- `org.opencontainers.image.title`
- `org.opencontainers.image.description`
- `org.opencontainers.image.source`
- `org.opencontainers.image.url`
- `org.opencontainers.image.vendor`
- `org.opencontainers.image.licenses`

## Build locally (optional)

If you want to rebuild an image locally, run from the repository root:

```bash
docker build -f src/java/Dockerfile -t graftcode/eclipse-temurin:21-jdk .
```

Replace the Dockerfile and tag for the image you want.

## License

This repository is published under the terms of the included `LICENSE` file.
