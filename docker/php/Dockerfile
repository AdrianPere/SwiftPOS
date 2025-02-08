FROM php:8.3-fpm

# Instalar extensiones necesarias
RUN apt-get update && apt-get install -y \
    libzip-dev unzip git libicu-dev libpq-dev libonig-dev \
    && docker-php-ext-install zip intl pdo pdo_mysql

# Instalar Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Configurar el directorio de trabajo
WORKDIR /var/www/html

CMD ["php-fpm"]
