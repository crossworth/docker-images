FROM php:5.6-fpm-alpine

EXPOSE 9000

RUN apk add --no-cache \
        nginx \
        libzip-dev \
        libpng-dev \
        zip \
        unzip \
        libjpeg-turbo-dev \
        freetype-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-configure zip --with-libzip \
    && docker-php-ext-install gd bcmath pdo_mysql mysqli zip pcntl

COPY php-fpm.d/docker.conf /usr/local/etc/php-fpm.d/zz-docker.conf
COPY php.ini /usr/local/etc/php/php.ini

CMD ["php-fpm"]