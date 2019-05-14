FROM kigawas/substrate-rust
ARG PROFILE=release
RUN apt update && apt install -y --no-install-recommends g++ cmake git libssl-dev pkg-config clang libclang-dev && git clone https://github.com/paritytech/substrate && cd substrate && ./scripts/build.sh && cargo build --$PROFILE && apt remove -y g++ cmake git libssl-dev pkg-config clang libclang-dev && apt autoremove -y && rm -rf /var/lib/apt/lists/*
