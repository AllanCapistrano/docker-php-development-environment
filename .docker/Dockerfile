
FROM php:7.4.33-apache

LABEL maintainer="AllanCapistrano <allan.capistrano3@gmail.com>"

# Copy application files to container
COPY . /var/www/html/

# Fix Debian Bullseye repositories
RUN sed -i '/deb.debian.org/s/^/#/' /etc/apt/sources.list \
    && echo "deb http://archive.debian.org/debian bullseye main" >> /etc/apt/sources.list \
    && echo "deb http://archive.debian.org/debian bullseye-updates main" >> /etc/apt/sources.list \
    && echo "deb [check-valid-until=no] http://snapshot.debian.org/archive/debian-security/20260903T220410Z/ bullseye-security main" >> /etc/apt/sources.list

# Install dependencies
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        libzip-dev \
        unzip \
        git \
        curl \
    && rm -rf /var/lib/apt/lists/*

# Install Composer
RUN curl -sS https://getcomposer.org/installer \
    | php -- --install-dir=/usr/local/bin --filename=composer \
    && composer --version

# Set file permissions
RUN chown -R www-data:www-data /var/www/html
