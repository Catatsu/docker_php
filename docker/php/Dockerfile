FROM php:7.3-fpm

RUN apt-get update -yqq \
	&& apt-get install -yqq --no-install-recommends \
	libicu-dev \
	git \
	zip \
	unzip \
	libmcrypt-dev \
	&& rm -rf /var/lib/apt/lists \
	&& docker-php-ext-configure intl \
	&& docker-php-ext-install intl pdo_mysql mysqli mbstring

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin/ --filename=composer
