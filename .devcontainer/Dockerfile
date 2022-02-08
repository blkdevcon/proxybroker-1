# # See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.217.1/containers/rust/.devcontainer/base.Dockerfile

# # [Choice] Debian OS version (use bullseye on local arm64/Apple Silicon): buster, bullseye
# ARG VARIANT="buster"
# FROM mcr.microsoft.com/vscode/devcontainers/rust:0-${VARIANT}

# # [Optional] Uncomment this section to install additional packages.
# # RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
# #     && apt-get -y install --no-install-recommends <your-package-list-here>

FROM rust:1.58.1-alpine

# Add vscode user
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID
RUN apk add sudo && \
  addgroup $USERNAME && \
  adduser -u $USER_UID -G $USERNAME -s /bin/sh -D $USERNAME && \
  echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME && \
  chmod 0440 /etc/sudoers.d/$USERNAME

# Install other utilities
RUN apk add git libc-dev openssl-dev