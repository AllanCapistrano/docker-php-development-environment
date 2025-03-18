FROM php:7.3-apache
LABEL maintainder="AllanCapistrano <allan.capistrano3@gmail.com>"

# Copy application files to container
COPY . /var/www/html/

RUN apt-get update

# Install libzip
RUN apt-get install -y libzip-dev

# Install unzip
RUN apt-get install -y unzip

# Install PDO
RUN docker-php-ext-install pdo_mysql

# Install git
RUN apt-get install -y git

# Install composer and make command global
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# Set property permissions to files
RUN chown -R www-data:www-data /var/www/html