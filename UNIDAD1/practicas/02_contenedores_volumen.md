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

```docker ```