FROM docker.io/caddy:2.11.4-builder-alpine AS builder

RUN xcaddy build \
    --with github.com/yroc92/postgres-storage \
    --with github.com/caddy-dns/cloudflare

### build caddy image
FROM docker.io/caddy:2.11.4-alpine

COPY --from=builder /usr/bin/caddy /usr/bin/caddy


