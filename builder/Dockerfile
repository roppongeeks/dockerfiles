FROM roppongeeks/rustup:latest 
LABEL maintainer="knarfytrebil@gmail.com"
LABEL description="Substrate"

ARG PROFILE=release

RUN git clone https://github.com/roppongeeks/substrate.git
RUN cd substrate && ./scripts/build.sh

RUN if [ "${PROFILE}" = "release" ]; then \
      cd substrate && cargo build --release; \
    else \
      cd substrate && cargo build; \
fi
