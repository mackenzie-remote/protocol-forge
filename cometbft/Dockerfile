FROM ghcr.io/mackenzie-remote/base-go1.21:jammy as BUILD
ARG git_repository=https://github.com/cometbft/cometbft
ARG git_version=main
RUN git clone --recursive --branch $git_version $git_repository /build_dir
WORKDIR /build_dir
RUN make install

FROM gcr.io/distroless/base-debian11:latest
ARG git_repository=https://github.com/cometbft/cometbft
ARG git_version=main
ARG name="cometbft"
ARG summary="Distroless container build for ${name}."
LABEL description="${summary}" \
      maintainer="cloudnull.io <kevin@cloudnull.com>" \
      app.kubernetes.io/name="${name}" \
      app.kubernetes.io/version="${git_version}" \
      org.opencontainers.image.title="${name}" \
      org.opencontainers.artifact.description="${summary}" \
      org.opencontainers.image.url="https://github.com/oshied/protocol-forge" \
      org.opencontainers.image.authors="kevin@cloudnull.com" \
      org.opencontainers.image.revision="${git_version}" \
      org.opencontainers.image.source="${git_repository}" \
      org.opencontainers.image.vendor="cloudnull.io" \
      org.opencontainers.image.description="${summary}"
WORKDIR /usr/local/bin
COPY --from=BUILD /root/go/bin/cometbft /usr/local/bin/cometbft
ENTRYPOINT ["/usr/local/bin/cometbft"]
