FROM php:5-fpm-alpine

RUN apk add --update ca-certificates  zlib-dev libmcrypt-dev && rm -rf /var/cache/apk/* \
    && docker-php-ext-install gd mcrypt mysqli mysqlnd pdo pdo_mysql zip

EXPOSE 9000
CMD ["php-fpm"]
