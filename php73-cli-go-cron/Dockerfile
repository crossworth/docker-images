FROM php:7.3-cli-alpine

RUN apk add --no-cache curl
RUN curl -L --insecure https://github.com/odise/go-cron/releases/download/v0.0.6/go-cron-linux.gz | zcat > /usr/local/bin/go-cron
RUN chmod u+x /usr/local/bin/go-cron

RUN apk add --no-cache \
        libzip-dev \
        libpng-dev \
        zip \
        git \
        unzip \
        libjpeg-turbo-dev \
        freetype-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-configure zip --with-libzip \
    && docker-php-ext-install gd bcmath pdo_mysql zip pcntl


