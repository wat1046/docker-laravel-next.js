FROM php:7.4-fpm

COPY php.ini /usr/local/etc/php/

RUN apt-get update && apt-get install -y \
  unzip \
  libzip-dev \
  zlib1g-dev \
  libpq-dev \
  && docker-php-ext-install \
  zip \
  pdo_mysql \
  pdo_pgsql \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* \
  && curl https://cli-assets.heroku.com/install.sh | sh

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -SL https://deb.nodesource.com/setup_lts.x | bash
RUN apt-get install -y nodejs && \
  npm install -g npm@latest

RUN apt-get install -y git
  
WORKDIR /var/www/html