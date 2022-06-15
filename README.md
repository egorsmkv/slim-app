Add a line to /etc/hosts:

```
echo "127.0.0.1 yewater-website.local.local" | sudo tee -a /etc/hosts
```

Install:

```
openssl req -newkey rsa:2048 -nodes -keyout ssl/key.pem -x509 -days 365 -out ssl/cert.pem -config ssl/openssl.conf

docker-compose -f docker-compose.dev.yml build

docker-compose -f docker-compose.dev.yml up

docker exec -it yewater-website_apps_1 bash

cd /app/frontend && php composer.phar install

cd apps/frontend/
# edit .env by yourself
cp .env.dev.example .env

php artisan key:generate

# todo: fix this
chmod -R 777 /app

php artisan migrate
```
