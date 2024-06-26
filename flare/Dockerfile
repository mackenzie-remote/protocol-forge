FROM ghcr.io/mackenzie-remote/base-go1.19:bionic as BUILD
ARG git_repository=https://github.com/flare-foundation/go-flare
ARG git_version=main
RUN git clone --recursive --branch $git_version $git_repository /build_dir
WORKDIR /build_dir/avalanchego
RUN apt update && apt install -y rsync
RUN ./scripts/build.sh

FROM gcr.io/distroless/base-debian11:latest
ARG git_repository=https://github.com/flare-foundation/go-flare
ARG git_version=main
ARG name="flare"
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
COPY --from=BUILD /build_dir/avalanchego/build/avalanchego /usr/local/bin/avalanchego
COPY --from=BUILD /build_dir/avalanchego/build/plugins /usr/local/bin/plugins
ENTRYPOINT ["/usr/local/bin/avalanchego"]
