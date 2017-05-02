IMG = do-caddy-root
INST = do-caddy-root1

HTML = /mnt/volume-sfo2-01/cj/carltonjosephdotcom

build:
	docker build -t $(IMG) .

run:
	docker run --name $(INST) -d -p 80:80,443:443 \
	-v $(HTML):/html \
	$(IMG)

runAlways:
	docker run --restart=always --name $(INST) -d -p 80:80,443:443 \
	-v $(HTML):html \
	$(IMG)

update:
	docker cp Caddyfile $(INST):/Caddyfile
#	docker exec $(INST) nginx -s reload # need to figure out how to restart the caddy server

clean:
	docker rm -f $(shell docker ps -a | grep $(INST) | cut -b 1-12)

rerun: stopnrun1 run

stopnrun1: stopnrun2 build

stopnrun2: clean
