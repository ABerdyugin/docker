FROM php:8.3-fpm
WORKDIR /var/www
# Устанавливаем зависимости
RUN apt-get update && apt-get install -y \
    mc \
    build-essential \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    locales \
    zip \
    jpegoptim optipng pngquant gifsicle \
    vim \
    unzip \
    git \
    curl \
    libpq-dev \
    libonig-dev \
    libzip-dev \
    libxml2-dev \
    htop

# Очищаем кэш
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install pdo pdo_mysql gd zip xml iconv simplexml

# Загружаем актуальную версию Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php-fpm"]