FROM php:8.0-fpm

WORKDIR /usr/share/nginx/html

RUN apt-get update \
    && apt-get install -y mariadb-server 

EXPOSE 3306 


LABEL version="1.0"
LABEL description="MariaDB Server"

HEALTHCHECK --start-period=5m \
  CMD mariadb -e 'SELECT @@datadir;' || exit 1

CMD ["mysqld"]

RUN apt-get update -y \
    && apt-get install -y libpng-dev libfreetype6-dev libyaml-dev \
    && apt-get install -y \
               zlib1g-dev \
               zip \
    && docker-php-ext-install zip

RUN php composer-setup.php --install-dir=bin --filename=composer \
    mv composer.phar /usr/local/bin/composer \
    php bin/composer

RUN pecl install yamL

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/freetype2 \
    && docker-php-ext-install gd \
    && docker-php-source delete



# Workaround for write permission on write to MacOS X volumes
# See https://github.com/boot2docker/boot2docker/pull/534
RUN usermod -u 1000 www-data

COPY php.ini /usr/local/etc/php/


