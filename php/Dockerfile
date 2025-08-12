FROM php:8.2-fpm


RUN apt-get update && apt-get install -y \
    libpq-dev \
    libzip-dev \
    zip \
    autoconf g++ make \
    && docker-php-ext-install pdo pdo_pgsql zip \
    && rm -rf /var/lib/apt/lists/*


RUN pecl install xdebug-3.2.1 && docker-php-ext-enable xdebug


RUN echo "xdebug.mode=debug" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
    && echo "xdebug.client_host=host.docker.internal" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
    && echo "xdebug.start_with_request=yes" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini