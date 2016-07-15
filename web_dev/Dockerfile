FROM php:5.6-apache
MAINTAINER usart <andrey@ushakov.spb.ru>

RUN a2enmod rewrite
RUN a2enmod headers
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        locales
RUN docker-php-ext-install -j$(nproc) iconv mcrypt 
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-install -j$(nproc) mysqli
RUN docker-php-ext-install -j$(nproc) mbstring
RUN docker-php-ext-install -j$(nproc) zip
RUN locale-gen ru_RU.UTF-8
