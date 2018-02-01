FROM php:7-fpm-alpine

ENV PHPREDIS_VERSION 3.0.0

RUN apk add --update ca-certificates zlib-dev libpng-dev libressl-dev libsodium-dev git postgresql-dev && rm -rf /var/cache/apk/* \
    && docker-php-ext-install gd pcntl mysqli pdo pdo_mysql pgsql sodium pdo_pgsql zip bcmath sockets posix shmop

RUN mkdir -p /usr/src/php/ext/redis \
    && curl -L https://github.com/phpredis/phpredis/archive/$PHPREDIS_VERSION.tar.gz | tar xvz -C /usr/src/php/ext/redis --strip 1 \
    && echo 'redis' >> /usr/src/php-available-exts \
    && docker-php-ext-install redis


EXPOSE 9000

CMD ["php-fpm"]
