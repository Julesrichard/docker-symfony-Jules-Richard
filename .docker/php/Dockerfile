FROM php:8.1.5-fpm

LABEL author="Khalid Sookia"

RUN apt update \
    && apt install -y --no-install-recommends vim curl debconf git apt-transport-https apt-utils \
    build-essential locales acl mailutils wget zip unzip libsodium-dev \
    libpng-dev libicu-dev libzip-dev libxml2-dev libexif-dev wkhtmltopdf \
    gnupg gnupg1 gnupg2 \
    && docker-php-ext-install gd \
    && docker-php-ext-install intl \
    && docker-php-ext-install zip \
    && docker-php-ext-install pdo \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install xml \
    && docker-php-ext-enable gd \
    && docker-php-ext-enable intl \
    && docker-php-ext-enable zip \
    && docker-php-ext-enable pdo \
    && docker-php-ext-enable pdo_mysql \
    && docker-php-ext-enable xml

RUN echo 'date.timezone="Europe/Paris"' >> /usr/local/etc/php/conf.d/date.ini
RUN usermod -u 1000 www-data

RUN rm -rf /var/lib/apt/lists/*
RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    echo "fr_FR.UTF-8 UTF-8" >> /etc/locale.gen && \
    locale-gen

EXPOSE 9000
