FROM mcr.microsoft.com/devcontainers/javascript-node:24-bookworm

# Prisma needs OpenSSL at runtime; postgresql-client is handy for `psql`/`pg_isready` debugging.
# nasm/make: build tiny guest boot images for the client-side v86 VM (v86 itself
# ships prebuilt from npm — no Rust/wasm toolchain needed to consume it, only
# to hand-assemble custom guest boot sectors). xxd: inspecting disk images.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y --no-install-recommends openssl postgresql-client nasm make xxd \
    && apt-get clean && rm -rf /var/lib/apt/lists/*
