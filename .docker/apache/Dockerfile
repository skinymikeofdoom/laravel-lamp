FROM php:7.1.8-apache

ADD ./vhost.conf /etc/apache2/sites-available/default.conf

RUN chown -R www-data:www-data /var/www/ && a2enmod rewrite && a2ensite default

RUN apt-get update
RUN apt-get -y install apt-utils
RUN apt-get -y install git
RUN apt-get -y install mcrypt
RUN apt-get -y install php-pclzip
RUN apt-get -y install libpq-dev curl
RUN apt-get -y install libjpeg-dev
RUN apt-get -y install libpng12-dev
RUN apt-get -y install libfreetype6-dev
RUN apt-get -y install libssl-dev
RUN apt-get -y install libmcrypt-dev
RUN apt-get -y install curl
RUN apt-get -y install nano

RUN docker-php-ext-install mysqli
RUN docker-php-ext-enable mysqli
RUN docker-php-ext-install zip
RUN docker-php-ext-enable zip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


RUN apt-get update && \
    apt-get install -y --no-install-recommends git zip

RUN curl --silent --show-error https://getcomposer.org/installer | php

WORKDIR /var/www/

VOLUME /var/www/

RUN service apache2 restart
