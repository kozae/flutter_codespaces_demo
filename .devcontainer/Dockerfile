# Use Ubuntu as base image
FROM ubuntu:22.04

# Install dependencies
RUN apt-get update && apt-get install -y \
    curl \
    git \
    wget \
    unzip \
    lib32stdc++6 \
    libglu1-mesa \
    default-jdk \
    && rm -rf /var/lib/apt/lists/*

# Install Flutter
ENV FLUTTER_HOME="/opt/flutter" \
    PATH="/opt/flutter/bin:${PATH}"

# Install Flutter 3.24 (which includes Dart 3.5+)
RUN git clone https://github.com/flutter/flutter.git -b stable ${FLUTTER_HOME} && \
    flutter config --no-analytics && \
    flutter precache && \
    flutter doctor

# Set working directory
WORKDIR /workspace

# Expose port for Flutter web
EXPOSE 3000