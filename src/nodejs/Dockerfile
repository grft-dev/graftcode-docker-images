FROM node:22

LABEL org.opencontainers.image.title="Graftcode Gateway Node.js"
LABEL org.opencontainers.image.description="Node.js 22 image with Graftcode Gateway preinstalled"
LABEL org.opencontainers.image.source="https://github.com/grft-dev/graftcode-docker-images"
LABEL org.opencontainers.image.url="https://hub.docker.com/r/graftcode/node"
LABEL org.opencontainers.image.vendor="grft-dev"
LABEL org.opencontainers.image.licenses="MIT"

ARG GG_VERSION=
RUN set -eux; \
    if [ -n "${GG_VERSION}" ]; then \
      GG_URL="https://github.com/grft-dev/graftcode-gateway/releases/download/v${GG_VERSION}/gg_linux_amd64.deb"; \
    else \
      GG_URL="https://github.com/grft-dev/graftcode-gateway/releases/latest/download/gg_linux_amd64.deb"; \
    fi; \
    wget -O /tmp/gg.deb "${GG_URL}" && \
    dpkg -i /tmp/gg.deb && \
    rm /tmp/gg.deb

EXPOSE 80

CMD ["gg"]

