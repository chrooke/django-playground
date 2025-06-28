FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

# Install Python, pip, venv, and common tools
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        python3 \
        python3-pip \
        python3-venv \
        build-essential \
        git \
        curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Create a virtual environment in /opt/venv and install Django
RUN python3 -m venv /opt/venv && \
    /opt/venv/bin/pip install --no-cache-dir django

# Update PATH so /opt/venv/bin is first
ENV PATH="/opt/venv/bin:$PATH"

# Set working directory
WORKDIR /workspace

# Default command (can be overridden by devcontainer config)
CMD ["bash"]