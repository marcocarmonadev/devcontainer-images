FROM node:lts
RUN userdel --remove --force node \
    && npm completion >> /etc/bash.bashrc \
    && node --completion-bash >> /etc/bash.bashrc