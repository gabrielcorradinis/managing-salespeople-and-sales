FROM php:8.1-apache

COPY ./docker/php/etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/

RUN apt update && \
apt install -y zip cron && \
a2enmod rewrite && \
docker-php-ext-install pdo_mysql sockets && \
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
php composer-setup.php --filename=composer --install-dir=/bin --version=2.4.2 && \
php -r "unlink('composer-setup.php');"
