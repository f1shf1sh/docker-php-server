FROM php:7.4-fpm-alpine

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories \ 
    && docker-php-ext-install pdo_mysql \
    && apk add --no-cache ${PHPIZE_DEPS} \
    && pecl install redis-4.0.1 xdebug-3.1.1 \
    && docker-php-ext-enable redis xdebug \
    && apk del ${PHPIZE_DEPS}