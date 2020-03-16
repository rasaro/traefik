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

#### Docker swarm

```
docker network create --driver=overlay traefik
```

#### Docker compose

```
docker network create traefik
```

### Production mode

#### Run in docker swarm mode

```
docker stack deploy -c <(docker-compose -f docker-compose.yml -f docker-compose.prod.yml -f docker-compose.swarm.yml config) traefik
```

#### Run in docker compose mode

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

### Development mode

#### Run in docker swarm mode

```
docker stack deploy -c <(docker-compose -f docker-compose.yml -f docker-compose.dev.yml -f docker-compose.swarm.yml config) traefik
```

#### Run in docker compose mode

```
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
```
