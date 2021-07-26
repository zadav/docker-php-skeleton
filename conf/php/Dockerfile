FROM php:7.4-fpm

ENV COMPOSER_ALLOW_SUPERUSER=1

# git, unzip & zip are for composer
RUN apt-get update -qq && \
    apt-get install -qy \
    git \
    gnupg \
    unzip \
    zip && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install xdebug
RUN pecl install xdebug && docker-php-ext-enable xdebug
RUN docker-php-ext-install -j$(nproc) opcache pdo_mysql

WORKDIR /code

EXPOSE 9003