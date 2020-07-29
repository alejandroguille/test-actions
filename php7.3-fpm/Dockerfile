# See https://github.com/docker-library/php/blob/4677ca134fe48d20c820a19becb99198824d78e3/7.0/fpm/Dockerfile
FROM php:7.3.0-fpm

ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN apt-get update && apt-get install -y \
    git \
    libmcrypt-dev unzip zlib1g-dev libpng-dev libfreetype6-dev libjpeg-dev libfreetype6-dev libjpeg62-turbo-dev \
    wget gnupg apt-transport-https \
    libxml2-dev libzip-dev

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# Set timezone
RUN echo "America/Argentina/Buenos_Aires" > /etc/timezone
RUN dpkg-reconfigure -f noninteractive tzdata

RUN docker-php-ext-install pdo pdo_mysql 

#GD
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd zip

ADD www.conf /usr/local/etc/php-fpm.d

WORKDIR /var/www/laravel

#npm
RUN curl -sL https://deb.nodesource.com/setup_14.x  | bash -
RUN apt-get -y install nodejs
