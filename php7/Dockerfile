FROM php:7-fpm-alpine

RUN apk add --update ca-certificates zlib-dev libpng-dev libressl-dev git postgresql-dev && rm -rf /var/cache/apk/* \
    && docker-php-ext-install gd pcntl mysqli pdo pdo_mysql pgsql pdo_pgsql zip

EXPOSE 9000

CMD ["php-fpm"]
