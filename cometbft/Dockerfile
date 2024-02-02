FROM ghcr.io/mackenzie-remote/base-go1.21:jammy as BUILD
ARG git_repository=https://github.com/cometbft/cometbft
ARG git_version=main
RUN git clone --recursive --branch $git_version $git_repository /build_dir
WORKDIR /build_dir
RUN make install
