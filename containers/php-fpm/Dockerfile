FROM php:8.3-fpm

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get -y install libbz2-dev zlib1g-dev libpng-dev libgmp-dev libicu-dev libsqlite3-dev libtidy-dev libxslt1-dev libzip-dev && \
    apt-get autoremove -y && \
    apt-get clean -y && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /var/cache/apt/*

RUN docker-php-ext-install bcmath bz2 calendar dba exif ftp gd gettext gmp intl mysqli pcntl pdo pdo_mysql pdo_sqlite shmop soap sockets sysvmsg sysvsem sysvshm xsl zip
