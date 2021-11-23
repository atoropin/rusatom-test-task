FROM php:7.4-fpm-alpine

RUN set -ex \
    && apk --no-cache add \
        postgresql-dev make \
    && docker-php-ext-install pdo \
    && docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install pdo_pgsql

RUN apk upgrade --no-cache --update && apk add \
     postgresql-dev \

RUN curl -sS https://getcomposer.org/installer | php -- --version=2.1.12 --install-dir=/usr/local/bin --filename=composer

RUN apk add --no-cache git
