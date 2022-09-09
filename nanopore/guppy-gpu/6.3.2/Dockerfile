FROM ubuntu:bionic

ENV PATH="/guppy/ont-guppy/bin:$PATH"
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8

RUN apt update \
    && apt install -y software-properties-common \
    && apt-add-repository universe \
    && apt update \
    && apt install -y wget build-essential

# ================================
# INSTALL guppy-gpu
# ================================
ARG VERSION="6.3.2"
ARG URL="https://mirror.oxfordnanoportal.com/software/analysis/ont-guppy_${VERSION}_linux64.tar.gz"
WORKDIR /guppy
RUN ( wget -O - "$URL" | tar xzf - ) && command -v guppy_basecaller
