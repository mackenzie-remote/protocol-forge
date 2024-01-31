FROM ghcr.io/mackenzie-remote/base-go1.21:jammy as BUILD
ARG git_repository=https://github.com/osmosis-labs/osmosis
ARG git_version=main
RUN git clone --recursive --branch $git_version $git_repository /build_dir
WORKDIR /build_dir
RUN make build
RUN cp "$(ldd build/osmosisd | awk '/libwasmvm.x86_64.so/ {print $3}')" build/libwasmvm.x86_64.so
