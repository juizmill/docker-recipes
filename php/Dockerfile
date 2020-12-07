FROM php:8.0-fpm
RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y zlib1g-dev libicu-dev zip
RUN docker-php-ext-configure ctype \
    && docker-php-ext-install ctype
RUN docker-php-ext-configure intl \
    && docker-php-ext-install intl 
RUN pecl install xdebug-3.0.1 \
    && docker-php-ext-enable xdebug

RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini
RUN echo "xdebug.start_with_request = yes" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
RUN echo "xdebug.mode = debug" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
RUN echo "xdebug.idekey=VSCODE" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini