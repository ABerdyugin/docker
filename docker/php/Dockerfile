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


#ADD . /var/www
#RUN chgrp -R www-data /var/www
#RUN mkdir /var/www/v2
##RUN mkdir /var/www/v2/q
#RUN mkdir /var/www/v2/framework
#RUN mkdir /var/www/v2/framework/views
#RUN mkdir /var/www/v2/framework/sessions
#RUN mkdir /var/www/v2/framework/cache
#RUN mkdir /var/www/v2/storage
#RUN cd /var/www/v2/storage
#RUN chgrp www-data * -R
#RUN chmod g+w * -R

#COPY php-ini-local.conf /usr/local/etc/php-fpm.d/


CMD ["php-fpm"]