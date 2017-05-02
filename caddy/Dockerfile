FROM ubuntu:17.04
EXPOSE 80 443

COPY caddy /usr/bin/caddy

RUN mkdir -p /mnt/volume-sfo2-01/cj
COPY Caddyfile /etc/Caddyfile

WORKDIR /html

ENTRYPOINT ["/usr/bin/caddy"]
CMD ["--conf", "/etc/Caddyfile", "--log", "stdout"]
