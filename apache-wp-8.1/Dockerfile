FROM php:8.1-apache

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
# Set working directory
WORKDIR /web-wp

    ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && sync && \
    install-php-extensions mbstring

RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN docker-php-ext-install pdo && docker-php-ext-enable pdo    
RUN docker-php-ext-install pdo_pgsql && docker-php-ext-enable pdo_pgsql        
RUN docker-php-ext-install pdo_mysql && docker-php-ext-enable pdo_mysql        
RUN docker-php-ext-install opcache && docker-php-ext-enable opcache        
RUN docker-php-ext-install soap && docker-php-ext-enable soap        
RUN docker-php-ext-install bcmath && docker-php-ext-enable bcmath        
RUN docker-php-ext-install exif && docker-php-ext-enable exif        
RUN docker-php-ext-install iconv && docker-php-ext-enable iconv        
RUN docker-php-ext-install iconv && docker-php-ext-enable iconv        
RUN docker-php-ext-install intl && docker-php-ext-enable intl        
RUN docker-php-ext-install pcntl && docker-php-ext-enable pcntl        
RUN docker-php-ext-install gd && docker-php-ext-enable gd     


RUN apt-get update && apt-get upgrade -y 
