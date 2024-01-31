FROM ghcr.io/mackenzie-remote/base-build:focal as focal
ARG name="base-go1.21"
ARG summary="Base build image for go 1.21.x built on-top of ubuntu Focal"
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
ARG GO_URL=https://go.dev/dl/go1.21.6.linux-amd64.tar.gz
RUN rm -rf /usr/local/go
RUN curl -L "$GO_URL" -o /tmp/go-linux-amd64.tar.gz
RUN tar -C /usr/local -xzf /tmp/go-linux-amd64.tar.gz
ENV PATH="$PATH:/usr/local/go/bin"

FROM ghcr.io/mackenzie-remote/base-build:jammy as jammy
ARG name="base-go1.21"
ARG summary="Base build image for go 1.21.x built on-top of ubuntu Jammy"
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
ARG GO_URL=https://go.dev/dl/go1.21.6.linux-amd64.tar.gz
RUN rm -rf /usr/local/go
RUN curl -L "$GO_URL" -o /tmp/go-linux-amd64.tar.gz
RUN tar -C /usr/local -xzf /tmp/go-linux-amd64.tar.gz
ENV PATH="$PATH:/usr/local/go/bin"
