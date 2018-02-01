FROM php:7-zts-alpine

ENV PHPREDIS_VERSION 3.0.0
ENV EVENT_VERSION 2.3.0

RUN apk add --update ca-certificates zlib-dev libpng-dev libressl-dev libsodium-dev git postgresql-dev libevent-dev && rm -rf /var/cache/apk/* \
    && docker-php-ext-install gd pcntl mysqli pdo pdo_mysql pgsql sodium pdo_pgsql zip bcmath sockets posix shmop

RUN mkdir -p /usr/src/php/ext/redis \
    && curl -L https://github.com/phpredis/phpredis/archive/$PHPREDIS_VERSION.tar.gz | tar xvz -C /usr/src/php/ext/redis --strip 1 \
    && echo 'redis' >> /usr/src/php-available-exts \
    && docker-php-ext-install redis

RUN mkdir -p /usr/src/php/ext/event \
    && curl -L https://pecl.php.net/get/event-$EVENT_VERSION.tgz | tar xvz -C /usr/src/php/ext/event --strip 1 \
    && echo 'event' >> /usr/src/php-available-exts \
    && docker-php-ext-install event \
    && mv /usr/local/etc/php/conf.d/docker-php-ext-event.ini /usr/local/etc/php/conf.d/zz-docker-php-ext-event.ini

CMD ["php"]
