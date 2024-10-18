FROM node
RUN userdel --remove --force node \
    && npm completion >> /etc/bash.bashrc \
    && node --completion-bash >> /etc/bash.bashrc