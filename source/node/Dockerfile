ARG VARIANT
FROM node:${VARIANT}
RUN userdel --remove --force node \
    && npm completion >> /etc/bash.bashrc \
    && node --completion-bash >> /etc/bash.bashrc