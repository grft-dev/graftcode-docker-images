FROM php:8.4-cli-bookworm

LABEL org.opencontainers.image.title="Graftcode Gateway PHP"
LABEL org.opencontainers.image.description="PHP 8.4 image with Graftcode Gateway preinstalled"
LABEL org.opencontainers.image.source="https://github.com/grft-dev/graftcode-docker-images"
LABEL org.opencontainers.image.url="https://hub.docker.com/r/graftcode/php"
LABEL org.opencontainers.image.vendor="grft-dev"
LABEL org.opencontainers.image.licenses="MIT"

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget \
    ca-certificates \
    libcurl4-openssl-dev \
    libffi-dev \
    libonig-dev \
    libzip-dev \
    && docker-php-ext-install curl ffi mbstring zip \
    && rm -rf /var/lib/apt/lists/*

# Workaround: latest gg (1.4.10) — GMA issues on PHP; pin 1.4.9 until fixed (see team/Dawid).
ARG GG_VERSION=1.4.9
RUN wget -O /tmp/gg.deb \
      "https://github.com/grft-dev/graftcode-gateway/releases/download/v${GG_VERSION}/gg_linux_amd64.deb" && \
    dpkg -i --force-overwrite /tmp/gg.deb && \
    rm /tmp/gg.deb

EXPOSE 80

CMD ["gg"]
