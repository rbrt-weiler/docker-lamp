# docker-lamp

This is a Docker Compose-based setup for a typical LAMP - Linux, Apache, MySQL, PHP - stack. It includes:

- Apache 2.4
- MariaDB 11.4
- PHP 8.3

## Components

### Apache HTTP Server

The stack utilizes the vanilla Apache 2.4 image and adds support for the following modules:

- deflate_module
- proxy_module
- proxy_fcgi_module
- rewrite_module

The only other additional change is the inclusion of a vhost configuration.

### MariaDB Database Server

Plain MariaDB 11.4 with the root password set to `admin`.

### PHP 8.3 FPM

Vanilla PHP 8.3 in the FPM version with some modules added to the setup, namely:

- bcmath
- bz2
- calendar
- dba
- exif
- ftp
- gd
- gettext
- gmp
- intl
- mysqli
- pcntl
- pdo
- pdo_mysql
- pdo_sqlite
- shmop
- soap
- sockets
- sysvmsg
- sysvsem
- sysvshm
- xsl
- zip

## Data Management

All container configs can be found in the folder `containers`, while all application data should be stored in the `app/website` and `app/database` folders. The containers will automatically map those two directories to provide automatic data persitency.

## Usage

Copy your web app to `app/website` and, if necessary, your database to `app/database`.

`docker compose up -d` will build the containers (if necessary) and start the whole LAMP stack. It will also automatically publish port 80/tcp to the host machine for accessing the web app, along with port 3306/tcp for MariaDB connections.

`docker compose down` will shut down all containers.
