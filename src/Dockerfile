FROM caddy:2.8.4-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    -with github.com/WeidiDeng/caddy-cloudflare-ip \
    --with github.com/abiosoft/caddy-hmac \
    --with github.com/lolPants/caddy-requestid \
    --with github.com/mholt/caddy-webdav \
    --with github.com/abiosoft/caddy-json-parse \
    --with github.com/porech/caddy-maxmind-geolocation

FROM caddy:2.8.4

COPY --from=builder /usr/bin/caddy /usr/bin/caddy

