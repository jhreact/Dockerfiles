# Dockerfile PostGIS

## Info

Forked from [helmi03/docker-postgis](https://github.com/helmi03/docker-postgis)

This Dockerfile creates a container running PostGIS 2.1 in PostgreSQL 9.3

- expose port `5432`
- initializes a database in `/var/lib/postgresql/9.3/main`
- superuser in the database: `docker/docker`


## Install

- `docker build -t taojonesin/postgis:2.1 .` or `docker build -t taojonesin/postgis:2.1 github.com/jhreact/dockerfiles/postgis.git`
- `docker run -d taojonesin/postgis:2.1`


## Usage

To connect to database, use docker inspect CONTAINER and grep IPAddress, e.g.

```bash
CONTAINER=$(sudo docker run -d -t taojonesin/postgis:2.1)
CONTAINER_IP=$(sudo docker inspect -f '{{ .NetworkSettings.IPAddress }}' $CONTAINER)
psql -h $CONTAINER_IP -p 5432 -U docker -W postgres
```


## Persistance

You can mount the database directory as a volume to persist your data:

```bash
docker run -d -v $HOME/postgres_data:/var/lib/postgresql postgis:2.1
```

Makes sure first need to create source folder: `mkdir -p ~HOME/postgres_data`.

If you copy existing postgresql data, you need to set permission properly (chown/chgrp)


## Meta

Build with docker version `1.2.0`


## References

- Docker trusted build: [helmi03/docker-postgis](https://registry.hub.docker.com/u/helmi03/docker-postgis/)
- [stigi/dockerfile-postgresql](https://github.com/stigi/dockerfile-postgresql)
- [Docker PostgreSQL Service](http://docs.docker.io/en/latest/examples/postgresql_service/)
