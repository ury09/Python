# https://github.com/microsoft/vscode-dev-containers/blob/main/containers/python-3/README.md
ARG VARIANT=3.13-bookworm
FROM mcr.microsoft.com/vscode/devcontainers/python:${VARIANT}
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
COPY requirements.txt /tmp/pip-tmp/
RUN python3 -m pip install --upgrade pip \
    && python3 -m pip --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmp
RUN pipx install pre-commit \
    && pipx install ruff \
    && pipx ensurepath
    ENV PATH="/root/.local/bin:${PATH}"
