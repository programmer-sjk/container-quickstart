FROM php:7.4-fpm
MAINTAINER JeongKuk Seo <wjdrnr6662@gmail.com>

RUN apt-get update
RUN apt-get install -y curl \
                       wget \
                       zlib1g-dev \
                       libzip-dev \
                       git \
                       vim

RUN curl -sS https://getcomposer.org/installer | php 
RUN mv composer.phar /usr/bin/composer

RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN docker-php-ext-configure zip
RUN docker-php-ext-install zip 

RUN composer global require laravel/installer
ENV PATH $PATH:~/.composer/vendor/bin/

WORKDIR /source

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y nodejs
