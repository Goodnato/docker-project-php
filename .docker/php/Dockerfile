FROM php:8.0.2-fpm

RUN apt-get update && apt-get install -y \
    autoconf \
    build-essential \
    apt-utils \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    unzip \
    zip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-install pdo pdo_mysql

RUN pecl install redis && docker-php-ext-enable redis

COPY --from=composer /usr/bin/composer /usr/bin/composer

ARG UID
ARG PID

USER ${UID}:${PID}