FROM bitnami/php-fpm:8.0.11-prod

RUN apt update && apt install -y autoconf php-dev pkg-php-tools build-essential

RUN wget https://pecl.php.net/get/redis-5.3.4.tgz && tar xzf redis-5.3.4.tgz && cd redis-5.3.4 && phpize && ./configure && make && make install
