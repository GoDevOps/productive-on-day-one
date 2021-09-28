# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.191.1/containers/alpine/.devcontainer/base.Dockerfile

# [Choice] Alpine version: 3.14, 3.13, 3.12, 3.11
# ARG VARIANT="3.14"
# FROM mcr.microsoft.com/vscode/devcontainers/base:0-alpine-${VARIANT}

# ** [Optional] Uncomment this section to install additional packages. **
# RUN apk update \
#     && apk add --no-cache <your-package-list-here>

# Dockerfile used by CI pipeline to publish doc site automatically
FROM mcr.microsoft.com/vscode/devcontainers/python:3.9
ENV MARP_VERSION=1.4.0
# ENV MARP_INPUT_PATH
# ENV MARP_OUTPUT_PATH
ENV PATH=$PATH:/usr/local/bin

COPY requirements.txt /requirements.txt
# RUN pwd && ls -al && env
RUN apt-get update -y && \
    apt-get install -y git \
        build-essential \
        python3-cffi \
        libcairo2 \
        libpango-1.0-0 \
        libpangocairo-1.0-0 \
        libgdk-pixbuf2.0-0 \
        libffi-dev \
        shared-mime-info \
        wget
RUN python3 -m pip install -r requirements.txt && \
    wget https://github.com/marp-team/marp-cli/releases/download/v${MARP_VERSION}/marp-cli-v${MARP_VERSION}-linux.tar.gz -O marp.tar.gz &&\
   	tar xvf marp.tar.gz -C /usr/local/bin


# ENTRYPOINT ["entrypoint.sh"] 