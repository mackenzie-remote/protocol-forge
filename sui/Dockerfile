FROM ghcr.io/mackenzie-remote/base-rustup:jammy as BUILD
ARG git_repository=https://github.com/MystenLabs/sui
ARG git_version=main
RUN git clone --recursive --branch $git_version $git_repository /build_dir
WORKDIR /build_dir
ENV PATH="$PATH:$HOME/.cargo/bin"
RUN /root/.cargo/bin/rustup toolchain install 1.75.0-x86_64-unknown-linux-gnu
RUN /root/.cargo/bin/rustup default 1.75.0-x86_64-unknown-linux-gnu
RUN /root/.cargo/bin/rustup component add rustfmt
RUN /root/.cargo/bin/cargo build --release --bin sui-node
RUN /root/.cargo/bin/cargo build --release --bin sui
