FROM php:fpm

RUN apt-get update
RUN apt-get -y install webp --no-install-recommends
RUN docker-php-ext-install pdo_mysql
RUN pecl install redis && docker-php-ext-enable redis
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
