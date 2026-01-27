# syntax=docker/dockerfile:1
ARG VARIANT="3.12-bookworm"
# https://hub.docker.com/r/microsoft/devcontainers-python
FROM mcr.microsoft.com/vscode/devcontainers/python:1-${VARIANT}

ARG UV_VERSION="0.9.26"
ARG MARIMO_VERSION="latest"
ARG RUFF_VERSION="latest"
ARG TY_VERSION="latest"
# you can also specify multiple Python versions separated by spaces.
ARG PYTHON_VERSION="3.12"

RUN mkdir /workspace && sudo chown vscode:vscode /workspace
RUN usermod -a -G dialout vscode

USER vscode
WORKDIR /home/vscode

# install uv with a specific version
# https://docs.astral.sh/uv/getting-started/installation/#installing-uv
RUN curl -LsSf https://astral.sh/uv/${UV_VERSION}/install.sh | sh
ENV PATH="/home/vscode/.local/bin:${PATH}"
RUN mkdir -p /home/vscode/.cache/uv

RUN uv tool install marimo@${MARIMO_VERSION} && \
    uv tool install ruff@${RUFF_VERSION} && \
    uv tool install ty@${TY_VERSION}

RUN uv python install ${PYTHON_VERSION}
