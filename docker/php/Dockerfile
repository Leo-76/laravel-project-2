FROM php:8.2-fpm

RUN apt-get update && apt-get install -y \
    build-essential libpng-dev libjpeg62-turbo-dev \
    libfreetype6-dev locales zip unzip git curl \
    libzip-dev libonig-dev \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install pdo_mysql mbstring zip exif pcntl
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install gd

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www
COPY . .
RUN composer install --no-dev --optimize-autoloader

EXPOSE 9000
CMD ["php-fpm"]
