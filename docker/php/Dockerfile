FROM php:7.2-fpm
MAINTAINER huko89088@qq.com
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install zip \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install opcache \
    && docker-php-ext-install mysqli

RUN pecl install redis-4.0.1 \
    && pecl install xdebug-2.6.0 \
    && pecl install swoole \
    && docker-php-ext-enable redis xdebug swoole