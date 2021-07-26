FROM php:8.0.2-fpm

RUN apt-get update && apt-get install -y \
    apt-utils \
    autoconf \
    build-essential \
    curl \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libzip-dev \
    unzip \
    zip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-install pdo pdo_mysql zip

RUN pecl install redis && docker-php-ext-enable redis

ARG APP_ENV
ARG XDEBUG_START
ARG XDEBUG_IDEKEY
ARG XDEBUG_CLIENT_HOST
ARG XDEBUG_CLIENT_PORT
ARG XDEBUG_LOG
RUN if [ "$APP_ENV" != 'production' ] ; then \
        yes | pecl install xdebug \
            && docker-php-ext-enable xdebug \
            && echo "xdebug.mode=debug" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
            && echo "xdebug.idekey=$XDEBUG_IDEKEY" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
            && echo "xdebug.client_host="$XDEBUG_CLIENT_HOST >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
            && echo "xdebug.client_port="$XDEBUG_CLIENT_PORT >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
            && echo "xdebug.start_with_request=$XDEBUG_START" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
    ; fi

COPY --from=composer /usr/bin/composer /usr/bin/composer

ARG UID
ARG PID

USER ${UID}:${PID}