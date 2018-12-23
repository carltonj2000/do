FROM ubuntu:16.04
EXPOSE 80 443

COPY caddy /usr/bin/caddy

RUN apt-get update; exit 0
RUN apt-get install -y curl
RUN mkdir -p /mnt/volume-sfo2-01/cj
COPY Caddyfile /etc/Caddyfile

WORKDIR /html

ENTRYPOINT ["/usr/bin/caddy"]
CMD ["-agree", "--conf", "/etc/Caddyfile", "--log", "stdout"]
