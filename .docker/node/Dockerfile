FROM node:14.16

ARG UID
ARG USERNAME

RUN userdel -r node
RUN useradd -m ${USERNAME} -s /bin/bash -u ${UID} -G sudo
USER ${USERNAME}