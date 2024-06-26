FROM ubuntu:20.04 as focal
ARG name="base-build"
ARG summary="Base build image built on-top of ubuntu Focal"
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
ENV DEBIAN_FRONTEND="noninteractive"
RUN apt-get update && apt-get install -y gpg wget curl git software-properties-common && rm -rf /var/lib/apt/lists/*
RUN git config --global --add safe.directory '*'
RUN git config --global submodule.recurse true
RUN curl https://apt.kitware.com/kitware-archive.sh -sSf | sh
RUN add-apt-repository -y ppa:ubuntu-toolchain-r/test
RUN apt-get update && apt-get install -y apt-utils autoconf automake build-essential clang clang-format cmake \
                                 direnv g++-9 gcc-9 git libboost-all-dev libbz2-dev libclang-dev libgflags-dev \
                                 libgmp3-dev liblz4-dev libsnappy-dev libssl-dev libtool libudev-dev \
                                 libusb-1.0-0-dev libusb-dev libzstd-dev llvm make pkg-config python3-dev \
                                 rsync software-properties-common sudo unzip zlib1g-dev && rm -rf /var/lib/apt/lists/*

FROM ubuntu:22.04 as jammy
ARG name="base-build"
ARG summary="Base build image built on-top of ubuntu Jammy"
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
ENV DEBIAN_FRONTEND="noninteractive"
RUN apt-get update && apt-get install -y gpg wget curl git software-properties-common && rm -rf /var/lib/apt/lists/*
RUN git config --global --add safe.directory '*'
RUN git config --global submodule.recurse true
RUN apt-get update && apt-get install -y apt-utils autoconf automake build-essential clang clang-format cmake \
                                 direnv g++-9 gcc-9 git libboost-all-dev libbz2-dev libclang-dev libgflags-dev \
                                 libgmp3-dev liblz4-dev libsnappy-dev libssl-dev libtool libudev-dev \
                                 libusb-1.0-0-dev libusb-dev libzstd-dev llvm make pkg-config python3-dev \
                                 rsync software-properties-common sudo unzip zlib1g-dev && rm -rf /var/lib/apt/lists/*
