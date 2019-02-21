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
docker exec -it jcg-nginx bash
docker exec -it jcg-db bash
docker exec -it jcg-mailhog bash
docker exec -it jcg-elasticsearch bash
```


# Licence
This package is an open-sourced software licensed under the MIT license.

