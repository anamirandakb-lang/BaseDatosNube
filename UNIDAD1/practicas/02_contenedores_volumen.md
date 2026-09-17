# Practica 2 CONTENEDORES CON VOLUMEN 

## Contenedor de Mariadb sin volumen

> para utilizar en distintos sistemas: 
```docker
docker run --name servermariadb `
-d -p 3310:3306 `
--env MARIADB_ROOT_PASSWORD=12345 `
--env MARIADB_USER=user-ejemplo `
--env MARIADB_PASSWORD=12345 `
--env MARIADB_DATABASE=world-db `
e101f9db

docker run --name servermariadb \
-d -p 3310:3306 \
--env MARIADB_ROOT_PASSWORD=12345 \
--env MARIADB_USER=user-ejemplo \
--env MARIADB_PASSWORD=12345 \
--env MARIADB_DATABASE=world-db \
e101f9db
```
## Comandos esenciales

` docker ps ` -> visualiza los contenedores en ejecucion

` docker container ls ` -> vizualiza los contenedores en ejecucion

` docker ps -a ` -> vizualiza todos los contenedores en ejecucion o no

`docker ls -a ` -> vizualiza todods los contenedores esten o no en ejecucion


## Creacion de volumenes

`docker volume create world-bd-vol` -> crear un volumen 

`docker volume ls ` -> vizualiza los volumenes

```docker

docker run --name servermariadb \
-d -p 3310:3306 \
--env MARIADB_ROOT_PASSWORD=12345 \
--env MARIADB_USER=user-ejemplo \
--env MARIADB_PASSWORD=12345 \
--env MARIADB_DATABASE=world-db \
-v world-db-vol:/var/lib/mysql \
e101f9db
```

## Creacion de volumenes

`docker volume create world-bd-vol` -> crear un volumen 

`docker volume ls ` -> vizualiza los volumenes


```docker
docker container run --name phpmyadmin \
-dp 8080:80 \
--env PMA_ARBITRARY=1 \
7c875148
```

## Crear una red 

` docker network create nombredelared ` -> crear una red

- ejempo : ` docker network create world-net`

` docker network ls` -> listas las redes

## Agregar contenedores a la red

`docker ps` -> para listarlos

` docker network connect nombredelared nombredelcontenedor` -> conectar el contenedor a la red 
- ejemplo: `docker network connect world-net phpmyadmin`

`docker network inspect nombredelared ` -> informacion de la red
- ejemplo : `docker network inspect worl-net`

