FROM php:8.1-apache
COPY test.conf /etc/apache2/sites-enabled/test.conf
RUN apt-get update
RUN a2enmod rewrite
#opcache
RUN docker-php-ext-install opcache
#gd
RUN apt-get install -y \
libfreetype-dev \
libjpeg62-turbo-dev \
libpng-dev
RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
&& docker-php-ext-install -j$(nproc) gd
#data base
RUN docker-php-ext-install mysqli pdo pdo_mysql
# RUN apt-get install -y \
# libxslt-dev \
# libxml2-dev \
# libmcrypt-dev \
# bzip2 \
# libbz2-dev \
# libfreetype-dev \
# libjpeg62-turbo-dev \
# libpng-dev
# RUN pecl install mcrypt-1.0.5
# RUN docker-php-ext-enable mcrypt
# RUN a2enmod rewrite
# # Install any extensions you need
# RUN docker-php-ext-install bz2
# RUN docker-php-ext-install calendar
# RUN docker-php-ext-install exif
# RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
# && docker-php-ext-install -j$(nproc) gd
# RUN docker-php-ext-install gettext
# RUN docker-php-ext-install mysqli
# RUN docker-php-ext-install mysqli pdo pdo_mysql
# RUN docker-php-ext-install pcntl
# RUN docker-php-ext-install shmop
# RUN docker-php-ext-install soap
# RUN docker-php-ext-install sockets
# RUN docker-php-ext-install sysvmsg
# RUN docker-php-ext-install sysvsem
# RUN docker-php-ext-install sysvshm
# RUN docker-php-ext-install xsl

EXPOSE 80