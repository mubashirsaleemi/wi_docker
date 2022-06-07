FROM php:5.6.40-apache
# Update APT
RUN apt-get update
# Install mcrypt dependency
RUN apt-get install -y libmcrypt-dev
# Install php mysqli, pdo, pdo_mysql, mcript plugin
RUN docker-php-ext-install pdo pdo_mysql mysqli mcrypt
# Enable apache rewrite
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf
# Copy php ini
COPY php.ini /usr/local/etc/php/php.ini
# Enable rewrite module
RUN a2enmod rewrite
# Enable environment module
RUN a2enmod env