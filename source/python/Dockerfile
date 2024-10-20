ARG VARIANT
FROM python:${VARIANT}
ENV UV_LINK_MODE=copy
COPY --from=ghcr.io/astral-sh/uv /uv /uvx /bin/
RUN echo 'eval "$(uv generate-shell-completion bash)"' >> /etc/bash.bashrc \
    && echo 'eval "$(uvx --generate-shell-completion bash)"' >> /etc/bash.bashrc