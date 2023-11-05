# Dockerized Slim app

```bash
openssl req -newkey rsa:2048 -nodes -keyout ssl/key.pem -x509 -days 365 -out ssl/cert.pem -config ssl/openssl.conf

docker-compose -f docker-compose.dev.yml build

docker-compose -f docker-compose.dev.yml up

docker exec -it slim-app_apps_1 bash

cd /app/frontend && php composer.phar install
```
