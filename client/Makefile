up:
	cd ../docker && docker-compose up -d

recreate:
	cd ../docker && docker-compose up -d --force-recreate

build:
	cd ../docker && docker-compose build

stop:
	cd ../docker && docker-compose stop

restart:
	cd ../docker && docker-compose restart

ps:
	cd ../docker && docker-compose ps

logs:
	cd ../docker && docker-compose logs

bash:
	cd ../docker && docker-compose run application /bin/bash


.PHONY: up recreate stop restart ps logs
