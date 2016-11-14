FROM php:7-fpm-alpine

RUN apk add --update ca-certificates zlib-dev libmcrypt-dev git && rm -rf /var/cache/apk/* \
    && docker-php-ext-install gd pcntl mcrypt mysqli mysqlnd pdo pdo_mysql zip

EXPOSE 9000

CMD ["php-fpm"]
