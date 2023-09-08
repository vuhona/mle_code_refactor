FROM mcr.microsoft.com/devcontainers/python:3.9

# We want all outputs of a program to be flushed to stdout
# without buffering
ENV PYTHONUNBUFFERED 1

# Install telnet for network troubleshooting
RUN apt-get update && apt-get -y install telnet

# Clean unnecessary files
RUN apt full-upgrade -y && \
    apt autoremove -y && \
    apt autoclean -y && \
    rm -rf /var/lib/apt/lists/*

COPY requirements_dev.txt /tmp/pip-tmp/

RUN pip install --upgrade pip && \
    pip install -r /tmp/pip-tmp/requirements_dev.txt && \
    rm -rf /tmp/pip-tmp
