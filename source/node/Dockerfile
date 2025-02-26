ARG VARIANT
FROM node:${VARIANT}
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt update \
    && apt upgrade -y \
    && apt install -y sudo
RUN deluser --remove-home --remove-all-files node \
    && addgroup --gid 1000 devcontainer \
    && adduser --uid 1000 --gid 1000 devcontainer \
    && adduser devcontainer sudo \
    && echo "devcontainer ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/devcontainer \
    && npm completion >> /etc/bash.bashrc \
    && node --completion-bash >> /etc/bash.bashrc