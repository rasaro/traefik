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

### Development mode

Uses Docker compose

#### Create docker network

```
docker network create traefik
```

#### Run container

```
docker-compose up -d
```

### Production mode

Uses Docker swarm

#### Create docker network

```
docker network create --driver=overlay traefik
```

#### Run container

```
docker stack deploy -c <(docker-compose -f docker-compose.prod.yml config) traefik
```
