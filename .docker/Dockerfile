FROM php:8.1-fpm
RUN apt-get update && apt-get upgrade -y

# Install Node.js and npm
RUN apt-get install -y nodejs npm
RUN apt-get update && apt-get install -y \
    zlib1g-dev \
    libzip-dev \
    unzip
RUN docker-php-ext-install zip

# Install mysqli extension
RUN docker-php-ext-install mysqli pdo pdo_mysql && docker-php-ext-enable mysqli pdo pdo_mysql

# Install Composer from the official image
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

#WORKDIR /var/www/html
#RUN  php artisan key:generate && php artisan migrate:fresh —seed

EXPOSE 9000