FROM ghcr.io/mackenzie-remote/base-rustup:focal as BUILD
ARG git_repository=https://github.com/jito-foundation/jito-solana
ARG git_version=master
RUN git clone --recursive --branch $git_version $git_repository /build_dir
WORKDIR /build_dir
ENV PATH="$PATH:$HOME/.cargo/bin"
RUN /root/.cargo/bin/rustup toolchain install 1.74.0-x86_64-unknown-linux-gnu
RUN /root/.cargo/bin/rustup default 1.74.0-x86_64-unknown-linux-gnu
RUN /root/.cargo/bin/rustup component add rustfmt
RUN CI_COMMIT=$(git rev-parse HEAD) scripts/cargo-install-all.sh /build_dir
