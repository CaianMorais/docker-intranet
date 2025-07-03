FROM php:7.4-apache

RUN apt-get update && apt-get install -y \
    nano \
    apt-transport-https \
    curl \
    gnupg2 \
    unixodbc \
    unixodbc-dev \
    zip unzip git \
    libzip-dev \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libxml2-dev \
    libonig-dev \
    libpq-dev \
    libldap2-dev \
    libssl-dev \
    libcurl4-openssl-dev \
    libgssapi-krb5-2 \
    software-properties-common \
    && docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install ldap pdo pdo_mysql mysqli mbstring exif pcntl gd zip

RUN a2enmod rewrite

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer