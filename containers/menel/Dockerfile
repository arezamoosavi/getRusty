FROM rust:1.47.0-slim-buster

RUN apt-get update \
    && apt-get install -y ca-certificates tzdata \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /opt/menel
ADD ./menel ./opt/menel

WORKDIR /opt/menel
RUN cargo build --release

RUN chmod a+rwx ./target/release/menel

EXPOSE 8080
CMD ["./target/release/menel"]