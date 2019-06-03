FROM rust-base

RUN rustup default nightly-2018-04-04

WORKDIR /app
ADD . .
ENV DATABASE_URL=url

RUN cargo build --release

ENTRYPOINT ["/app/target/release/./hero-api"]
