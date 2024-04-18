FROM php:8.3-fpm

# Installing dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    mariadb-client \
    libonig-dev \
    libzip-dev \
    vim \
    git \
    && docker-php-ext-install pdo_mysql mysqli mbstring zip

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Installing composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=2.1.3

# Changing Workdir
WORKDIR /application
