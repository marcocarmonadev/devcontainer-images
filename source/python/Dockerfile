ARG VARIANT
FROM python:${VARIANT}
ENV UV_LINK_MODE=copy
COPY --from=ghcr.io/astral-sh/uv /uv /uvx /bin/
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt update \
    && apt upgrade -y \
    && apt install -y sudo
RUN addgroup --gid 1000 devcontainer \
    && adduser --uid 1000 --gid 1000 devcontainer \
    && adduser devcontainer sudo \
    && echo "devcontainer ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/devcontainer \
    && echo 'eval "$(uv generate-shell-completion bash)"' >> /etc/bash.bashrc \
    && echo 'eval "$(uvx --generate-shell-completion bash)"' >> /etc/bash.bashrc
USER devcontainer
CMD ["sleep infinity"]