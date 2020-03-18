# traefik

Configuration for Traefik proxy router

## Requirements

- Docker
- Docker compose

## Running

### Environment variables

Copy example file

```
cp .env.example .env
```

Fill in fields in `.env`

### Create docker network

```
docker network create --driver=overlay traefik
```

#### Run container

```
docker stack deploy -c <(docker-compose config) traefik
```
