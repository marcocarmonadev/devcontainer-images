ARG VARIANT
FROM debian:${VARIANT}
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt update \
    && apt upgrade -y \
    && apt install -y sudo
RUN adduser --system --group --no-create-home --shell /bin/bash --uid 1000 vscode \
    && usermod -aG sudo vscode
USER vscode
CMD ["sleep infinity"]