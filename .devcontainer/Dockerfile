FROM ghcr.io/astral-sh/uv:debian


RUN apt-get update && apt-get install -y \
    git \
    curl \
    vim \
    openjdk-17-jdk \
    && rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
ENV PATH="${JAVA_HOME}/bin:${PATH}"

WORKDIR /workspace

COPY . .

RUN uv sync

ENV PATH="/workspace/.venv/bin:${PATH}"
RUN echo "alias pip='uv pip'" >> /etc/bash.bashrc
