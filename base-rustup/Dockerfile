FROM ghcr.io/mackenzie-remote/base-build:focal as focal
ARG name="base-rustup"
ARG summary="Base build image for rust built on-top of ubuntu Focal"
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
RUN apt-get update && apt-get install -y libprotobuf-dev protobuf-compiler && rm -rf /var/lib/apt/lists/*
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH="$PATH:/root/.cargo/bin"

FROM ghcr.io/mackenzie-remote/base-build:jammy as jammy
ARG name="base-rustup"
ARG summary="Base build image for rust built on-top of ubuntu Jammy"
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
RUN apt-get update && apt-get install -y libprotobuf-dev protobuf-compiler && rm -rf /var/lib/apt/lists/*
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH="$PATH:/root/.cargo/bin"
