FROM php:7-fpm-alpine
RUN docker-php-ext-install pdo pdo_mysql
RUN apk update
RUN apk add sudo
CMD ["php-fpm"]