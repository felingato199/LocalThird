# Configurtation of Local third Apps
## List of third Apps
- Redis
- Postgresql
- Mongo
- Rabbit

## OS variables config
Create a file for each config in path configs
### Redis
No need 
### Postgresql
```
POSTGRES_DB=
POSTGRES_USER=
POSTGRES_PASSWORD=
DEBIAN_FRONTEND=noninteractive
TZ=America/Bogota
PGTZ='GMT-5'
```
### Mongo
```
MONGO_INITDB_ROOT_USERNAME=
MONGO_INITDB_ROOT_PASSWORD=
MONGO_INITDB_DATABASE=
```

### Rabbit
```
RABBITMQ_DEFAULT_USER=
RABBITMQ_DEFAULT_PASS=
```

## Volumes
### Redis
No need 
### Postgresql
list_core_pg_data
```
docker volume create list_core_pg_data
```
### Mongo
list_core_mongodata
```
docker volume create list_core_mongodata
```

### Rabbit
no need

## Network
confilist_apps_network
```
docker network create confilist_apps_network
```

# Note: No use the default .envs files, only are examples, each information file is very easy to hack.

## Deploy:
- in path docker deploy execute:  
```
docker compose up -d
```
- check all good:
```
docker compose ps
NAME                            IMAGE                  COMMAND                  SERVICE    CREATED              STATUS              PORTS
confilist_apps_postgres_v13.4   postgres:13.4-alpine   "docker-entrypoint.s…"   postgres   About a minute ago   Up About a minute   0.0.0.0:5432->5432/tcp, :::5432->5432/tcp
dockerdeploy-mongodb-1          mongo:4.4.28-focal     "docker-entrypoint.s…"   mongodb    About a minute ago   Up About a minute   0.0.0.0:27017->27017/tcp, :::27017->27017/tcp
dockerdeploy-rabbit-1           rabbitmq               "docker-entrypoint.s…"   rabbit     About a minute ago   Up About a minute   4369/tcp, 5671/tcp, 15691-15692/tcp, 25672/tcp, 0.0.0.0:5672->5672/tcp, :::5672->5672/tcp
dockerdeploy-redis-1            redis:alpine           "docker-entrypoint.s…"   redis      About a minute ago   Up About a minute   6379/tcp
```

