FROM rust:1.47.0-slim-buster

RUN apt-get update \
    && apt-get install -y ca-certificates tzdata \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /opt/seaside
ADD ./seaside ./opt/seaside

WORKDIR /opt/seaside
RUN cargo build --release

RUN chmod a+rwx ./target/release/seaside

EXPOSE 8000
# CMD ["./target/release/seaside"]