FROM php:8.1-fpm

ARG DEBIAN_FRONTEND=noninteractive
WORKDIR /var/www/html

RUN apt-get update && apt-get install -y \
    git curl unzip libpng-dev libjpeg62-turbo-dev libfreetype6-dev \
    libzip-dev libxml2-dev libicu-dev libgmp-dev libpq-dev \
    libsqlite3-dev libmariadb-dev libonig-dev libcurl4-openssl-dev \
    libmagickwand-dev libmemcached-dev libz-dev libxslt-dev \
    libwebp-dev libavif-dev

RUN docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp --with-avif

RUN docker-php-ext-install \
    bcmath calendar curl exif gd gmp intl mbstring mysqli opcache \
    pcntl pdo pdo_mysql pdo_pgsql pdo_sqlite sockets soap xsl zip

RUN pecl install redis memcached xdebug imagick
RUN docker-php-ext-enable redis memcached xdebug imagick

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN apt-get clean && rm -rf /var/lib/apt/lists/*
