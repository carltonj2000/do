IMG = php-apache
INST = php-apache-1

HTML = /mnt/volume-sfo2-01/cj/carltonjosephdotcom

build:
	docker build -t $(IMG) .

run:
	docker run --name $(INST) -d -p 80:80 \
	-v $(HTML):/var/www/html \
	$(IMG)

runAlways:
	docker run --restart=always --name $(INST) -d -p 80:80 \
	-v $(HTML):/var/www/html \
	$(IMG)

update:
	echo not implemented # need to figure out how to restart php-fpm

clean:
	docker rm -f $(shell docker ps -a | grep $(INST) | cut -b 1-12)

rerun: stopnrun1 run

stopnrun1: stopnrun2 build

stopnrun2: clean
