ARG VARIANT
FROM debian:${VARIANT}
COPY --from=amazon/aws-cli /usr/local/aws-cli /usr/local/aws-cli
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt update \
    && apt upgrade -y \
    && apt install -y sudo nodejs npm groff less bash-completion curl wget git nano tar man \
    && addgroup --gid 1000 devcontainer \
    && adduser --uid 1000 --gid 1000 devcontainer \
    && adduser devcontainer sudo \
    && echo "devcontainer ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/devcontainer \
    && ln -s /usr/local/aws-cli/v2/current/bin/aws /usr/local/bin/aws \
    && ln -s /usr/local/aws-cli/v2/current/bin/aws_completer /usr/local/bin/aws_completer \
    && npm completion >> /etc/bash.bashrc \
    && node --completion-bash >> /etc/bash.bashrc