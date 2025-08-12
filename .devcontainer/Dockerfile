# Flutter Development Container
FROM ubuntu:24.04

# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive

# Install system dependencies
RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    zip \
    libglu1-mesa \
    openjdk-17-jdk \
    wget \
    chromium-browser \
    && rm -rf /var/lib/apt/lists/*

# Create a non-root user
RUN useradd -ms /bin/bash developer
USER developer
WORKDIR /home/developer

# Clone Flutter from GitHub (always gets the latest stable)
RUN git clone https://github.com/flutter/flutter.git -b stable

# Set environment variables
ENV PATH="$PATH:/home/developer/flutter/bin:/home/developer/flutter/bin/cache/dart-sdk/bin"

# Configure Flutter
RUN flutter config --no-analytics
RUN flutter config --enable-web
RUN flutter precache --web

# Set Chrome executable for Flutter web
ENV CHROME_EXECUTABLE=/usr/bin/chromium-browser

# Set working directory
WORKDIR /workspace