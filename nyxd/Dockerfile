FROM ghcr.io/mackenzie-remote/base-go1.21:jammy as BUILD
ARG git_repository=https://github.com/nymtech/nyxd
ARG git_version=main
RUN git clone --recursive --branch $git_version $git_repository /build_dir
WORKDIR /build_dir
RUN make build
RUN cp "$(ldd build/nyxd | awk '/libwasmvm.x86_64.so/ {print $3}')" build/libwasmvm.x86_64.so

FROM gcr.io/distroless/base-debian11:latest
ARG git_repository=https://github.com/nymtech/nyxd
ARG git_version=main
ARG name="nyxd"
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
COPY --from=BUILD /build_dir/build/nyxd /usr/local/bin/nyxd
WORKDIR /usr/local/lib/nyxd
COPY --from=BUILD /build_dir/build/libwasmvm.x86_64.so /usr/local/lib/nyxd/libwasmvm.x86_64.so
ENV LD_LIBRARY_PATH=/usr/local/lib/nyxd
ENTRYPOINT ["/usr/local/bin/nyxd"]
