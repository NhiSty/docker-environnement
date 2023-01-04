FROM php:8.1-fpm
RUN apt-get update && apt-get upgrade -y

# Install Node.js and npm
RUN apt-get install -y nodejs npm

# Install mysqli extension
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli

# Install Composer from the official image
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

WORKDIR /var/www/html
RUN  php artisan key:generate && php artisan migrate:fresh —seed

EXPOSE 9000