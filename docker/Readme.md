# Requirements

- Docker
- Docker compose

## General disclaimer

**Do not use on production.** This image is meant to be use for development purposes only, the use of it on a production environment is all up to your entire responsibility.

## Includes

- PHP-FPM
- MySQL
- Nginx
- Redis
- MailHog
- Elasticsearch

## Install

Download and run:

```bash
docker-compose build --no-cache
```

> The `public/` folder must be present before build the image

Then add the config for your local environment

```bash
cp .docker.env.example .docker.env
```

After configuring your environment variables

```bash
docker-compose up -d
```

To stop 

```bash
docker-compose down
```

## Interacting with the containers

Use the interactive console

```bash
docker exec -it jcg-app bash
docker exec -it jcg-nginx sh
docker exec -it jcg-db bash
docker exec -it jcg-mailhog sh
docker exec -it jcg-elasticsearch bash
```

```bash
docker-compose build
docker-compose up -d

# To run commands like 'composer' on server 
docker-compose exec jcg-app bash

# To access the database command line
docker-compose exec jcg-db bash
:/# mysql -u root -p
mysql> show databases;
mysql> GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'mypassword';
mysql> FLUSH PRIVILEGES;
mysql> desc mysql.user;
mysql> select Host, User, authentication_string from mysql.user;
mysql> EXIT;
:/# exit

```

# Licence
This package is an open-sourced software licensed under the MIT license.

