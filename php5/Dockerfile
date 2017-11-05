FROM php:5-fpm-alpine

RUN apk add --update ca-certificates zlib-dev libpng-dev openssl-dev libmcrypt-dev git postgresql-dev && rm -rf /var/cache/apk/* \
    && docker-php-ext-install gd pcntl mcrypt mysqli pdo pdo_mysql pgsql pdo_pgsql zip

EXPOSE 9000
CMD ["php-fpm"]
