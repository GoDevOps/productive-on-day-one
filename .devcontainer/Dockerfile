# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.191.1/containers/alpine/.devcontainer/base.Dockerfile

# [Choice] Alpine version: 3.14, 3.13, 3.12, 3.11
# ARG VARIANT="3.14"
# FROM mcr.microsoft.com/vscode/devcontainers/base:0-alpine-${VARIANT}

FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu-20.04
ENV MARP_VERSION=1.4.0
# ENV MARP_INPUT_PATH
# ENV MARP_OUTPUT_PATH
ENV PATH=$PATH:/usr/local/bin

# Install marp
RUN wget https://github.com/marp-team/marp-cli/releases/download/v${MARP_VERSION}/marp-cli-v${MARP_VERSION}-linux.tar.gz -O marp.tar.gz &&\
   	tar xvf marp.tar.gz -C /usr/local/bin

# Install markdown-lint
RUN curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash - && sudo apt-get install nodejs && sudo npm install -g markdownlint-cli
