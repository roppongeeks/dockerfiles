FROM roppongeeks/rustup:latest 
LABEL maintainer="knarfytrebil@gmail.com"
LABEL description="Substrate"

ARG PROFILE=debug
RUN git clone https://github.com/roppongeeks/substrate.git
RUN cd substrate && ./scripts/build.sh
RUN cd substrate && cargo build --$PROFILE
