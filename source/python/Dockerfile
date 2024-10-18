FROM python:3.12
COPY --from=ghcr.io/astral-sh/uv /uv /uvx /bin/
RUN echo 'eval "$(uv generate-shell-completion bash)"' >> /etc/bash.bashrc \
    && echo 'eval "$(uvx --generate-shell-completion bash)"' >> /etc/bash.bashrc