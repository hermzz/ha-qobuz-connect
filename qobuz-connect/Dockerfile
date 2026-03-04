# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

ARG QOBUZ_VERSION="v0.7.1"

RUN apt update && apt install -y libasound2

RUN curl -sSLf https://github.com/SofusA/qobuz-player/releases/download/${QOBUZ_VERSION}/qobuz-player-aarch64-unknown-linux-gnu.tar.gz | tar xz && \
    mv ./qobuz-player /usr/bin/qobuz-player && \
    chmod +x /usr/bin/qobuz-player

# Copy root filesystem
COPY rootfs /