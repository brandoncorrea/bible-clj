from arm64v8/debian:bullseye-slim

WORKDIR /app

# Base Packages
RUN apt update
RUN apt install -y \
  git \
  curl \
  clang \
  cmake \
  ninja-build \
  unzip \
  build-essential \
  libgtk-3-dev \
  rlwrap \
  vim

# Dart
RUN curl -O https://storage.googleapis.com/dart-archive/channels/stable/release/latest/sdk/dartsdk-linux-arm64-release.zip
RUN unzip dartsdk-linux-arm64-release.zip -d /usr/local/
RUN echo "export PATH=\"\$PATH:/usr/local/dart-sdk/bin\"" >> /root/.profile
RUN rm dartsdk-linux-arm64-release.zip

# Flutter
RUN git clone https://github.com/flutter/flutter.git -b stable /usr/local/flutter
RUN echo "export PATH=\"\$PATH:/usr/local/flutter/bin\"" >> /root/.profile
RUN source /root/.profile
RUN flutter --disable-analytics
RUN flutter precache
RUN flutter config --no-analytics
RUN flutter config --enable-linux-desktop
RUN flutter config --enable-web
RUN flutter doctor

# Clojure CLI
RUN curl -LO https://github.com/clojure/brew-install/releases/latest/download/linux-install.sh
RUN chmod +x linux-install.sh
RUN ./linux-install.sh
RUN rm linux-install.sh

# JDK 21
RUN curl -LO https://github.com/adoptium/temurin21-binaries/releases/download/jdk-21.0.6%2B7/OpenJDK21U-jdk_aarch64_linux_hotspot_21.0.6_7.tar.gz
RUN tar -xzf OpenJDK21U-jdk_aarch64_linux_hotspot_21.0.6_7.tar.gz -C /usr/local/
RUN rm OpenJDK21U-jdk_aarch64_linux_hotspot_21.0.6_7.tar.gz
RUN echo "export PATH=\"\$PATH:/usr/local/jdk-21.0.6+7/bin\"" >> /root/.profile
