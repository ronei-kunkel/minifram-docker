FROM php:8.2-fpm

RUN echo 'deb http://deb.debian.org/debian bullseye main' >> /etc/apt/sources.list

RUN apt-get update
RUN export DEBIAN_FRONTEND=noninteractive \
 && apt-get install -y --force-yes libssl-dev \
 curl \
 libbz2-dev \
 libcurl4-gnutls-dev \
 libxml2-dev \
 libicu-dev \
 libmcrypt4 \
 libmemcached11 \
 openssl \
 libonig-dev \
 libpq-dev \
 libfreetype6-dev \
 libjpeg62-turbo-dev \
 libpng16-16

RUN pecl install apcu-5.1.22 && docker-php-ext-enable apcu

RUN docker-php-ext-install opcache \
 bcmath \
 bz2 \
 intl \
 mbstring \
 pdo \
 pdo_mysql

RUN docker-php-ext-configure gd
RUN docker-php-ext-install gd

RUN echo 'America/Sao_Paulo' >> /etc/timezone

RUN ln -sf /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime

EXPOSE 9000
EXPOSE 80
CMD ["php-fpm"]