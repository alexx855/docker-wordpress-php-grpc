# PHP 7.4 Apache Wordpress install with gRPC enabled and composer

The installation tool kit, provided here, include:

- PHP with Apache server, Composer, gRPC and Wordpress
- MariaDB/MySQL used for Wordpress database
- MailDev: SMTP mail client and mail debug utility
- PhpMyAdmin interface to connect to your MariaDB/MySQL database

You can automatically deploy a local docker wordpress site with all this in less than 5 minutes, on any machine using the following commands:

````bash
# Download the docker-php-composer-grpc-wordpress
git clone # TODO: update repo url
cd php-apache-wordpresss-docker-compose
docker-compose up -d --build

Visit your site at <http://localhost>

Default identification for your wordpress website admin:

  - `Username: wordpress`
  - `Password: wordpress`

Default identification for the phpMyAdmin interface:

  - `Username: root`
  - `Password: password`

**Useful set of commands to know**:

``` bash
# Stop and remove containers
docker-compose down
# Build, and start the wordpress website
docker-compose up -d --build
# Reset everything
docker-compose down
rm -rf  mysql/* wordpress/*

# Restore database
docker exec -i ${COMPOSE_PROJECT_NAME}_mysql mysql -u${DATABASE_USER} -p${DATABASE_PASSWORD} ${COMPOSE_PROJECT_NAME} < LOCAL_FILENAME.sql

# Execute Composer comands
docker exec -i ${COMPOSE_PROJECT_NAME}_wordpress composer install
````

## Windows users

Download WSL2 and enable WSL2 support on Docker HUB
