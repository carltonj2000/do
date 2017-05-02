FROM ubuntu:17.04
EXPOSE 80 443

COPY caddy /usr/bin/caddy

RUN apt-get update && apt-get install -y curl
RUN mkdir -p /mnt/volume-sfo2-01/cj
COPY Caddyfile /etc/Caddyfile

WORKDIR /html

ENTRYPOINT ["/usr/bin/caddy"]
CMD ["--conf", "/etc/Caddyfile", "--log", "stdout"]
