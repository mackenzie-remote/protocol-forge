FROM ghcr.io/mackenzie-remote/base-build:focal as focal
ARG name="base-nodejs-lts"
ARG summary="Base build image for nodejs built on-top of ubuntu Focal"
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
RUN curl -fsSL https://deb.nodesource.com/setup_lts.x | bash -
RUN apt install -y nodejs
RUN npm install --global yarn

FROM ghcr.io/mackenzie-remote/base-build:jammy as jammy
ARG name="base-nodejs-lts"
ARG summary="Base build image for nodejs built on-top of ubuntu Jammy"
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
RUN curl -fsSL https://deb.nodesource.com/setup_lts.x | bash -
RUN apt install -y nodejs
RUN npm install --global yarn
