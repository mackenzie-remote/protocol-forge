FROM ghcr.io/mackenzie-remote/base-go1.20:jammy as BUILD
ARG git_repository=https://github.com/ava-labs/avalanchego
ARG git_version=main
RUN git clone --recursive --branch $git_version $git_repository /build_dir
WORKDIR /build_dir
RUN ./scripts/build.sh
