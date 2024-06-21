FROM php:7.3-apache

RUN apt-get -y update && apt-get -y install nano
RUN apt-get update -yqq \
    && apt-get install -yqq \
	ca-certificates \
    	git \
    	gcc \
    	make \
    	wget \
    	mc \
    	curl \
    	supervisor \
    	sendmail \
        zlib1g-dev \
        zip \
        libpng-dev \
        exiftool \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libicu-dev \
        libpq-dev \
        libxpm-dev \
        libvpx-dev \
        mariadb-client \
        libxml2-dev
RUN docker-php-ext-install \
	exif \
	bcmath \
	intl \
	pcntl \
	mysqli \
	pdo \
	gd \
	pdo_mysql \
	pdo_pgsql \
	mbstring \
	soap \
	opcache \
	iconv
RUN docker-php-ext-enable mbstring
RUN pecl install redis-5.1.1 \
    && pecl install xdebug-2.8.1 \
    && docker-php-ext-enable redis xdebug