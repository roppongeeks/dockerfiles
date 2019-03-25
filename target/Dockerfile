FROM debian:stretch-slim
LABEL maintainer="knarfytrebil@gmail.com"
LABEL description="Substrate"

ARG PROFILE=release

RUN apt-get update && \
    apt-get upgrade -y && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
		libssl-dev \
		ca-certificates \
		curl && \
    apt-get autoremove -y && \
    apt-get clean

RUN find /var/lib/apt/lists/ -type f -not -name lock -delete

COPY --from=roppongeeks/substrate:dev /root/substrate/target/$PROFILE/substrate /usr/local/bin

RUN useradd -m -u 1000 -U -s /bin/sh -d /substrate substrate
USER substrate

ENV RUST_BACKTRACE 1

EXPOSE 30333 9933 9944
VOLUME ["/substrate"]

ENTRYPOINT ["/usr/local/bin/substrate"]
