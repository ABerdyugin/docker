FROM php:5.6-fpm-alpine3.8

ENV TZ=America/New_York
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone


RUN apk update
RUN apk add mc

RUN docker-php-ext-install pdo pdo_mysql mysql
#
#RUN apk add libzip-dev
#RUN docker-php-ext-install  zip
#COPY ./conf.d/custom.ini /usr/local/etc/php/conf.d/custom.ini

# Загружаем актуальную версию Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
WORKDIR /var/www
CMD ["php-fpm"]