FROM debian:buster-slim

ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8

RUN apt update \
    && apt install -y wget

# ================================
# Download the f5c binaries
# ================================
ARG VERSION="0.6"
ARG URL="https://github.com/hasindu2008/f5c/releases/download/v${VERSION}/f5c-v${VERSION}-binaries.tar.gz"
WORKDIR /f5c
RUN ( wget -O - "$URL" | tar -xzf - --strip-components 1 --no-same-owner ) \
    && mv f5c_x86_64_linux_cuda /bin/f5c \
    && cd / \
    && rm -rf /f5c \
    && f5c --version
