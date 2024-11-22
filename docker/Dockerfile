FROM php:8.3-fpm

# Installing dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    mariadb-client \
    libonig-dev \
    libzip-dev \
    vim \
    git \
    nodejs \
    npm \
    && pecl install xdebug \
    && docker-php-ext-install pdo_mysql mysqli mbstring zip \
    && docker-php-ext-enable xdebug

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Installing composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=2.7.6

# Changing Workdir
WORKDIR /application
