# Apunte de Docker

##  Conceptos Fundamentales
* **Docker Hub**: Plataforma oficial para buscar y descargar imágenes. Se recomienda dar prioridad siempre a las **imágenes oficiales**.
* **Imágenes vs Contenedores**: A partir de una sola imagen se pueden desplegar múltiples contenedores independientes.
* **Ciclo de vida**: Los contenedores son efímeros y tienen un propósito o fin específico.
* **Tags (Etiquetas)**: Representan las versiones de la imagen. La etiqueta `latest` hace referencia a la versión más actualizada y estable.

---

## Comandos Esenciales de Gestión

### Descarga de Imágenes
```bash
git pull <nombre-imagen>
```

### Inspección del Sistema
* `docker images` — Lista todas las imágenes disponibles localmente.
* `docker ps` o `docker container ls` — Muestra únicamente los contenedores **activos/encendidos**.
* `docker ps -a` — Muestra **todos** los contenedores del sistema (activos e inactivos).
* `docker ps -l` — Muestra el **último** contenedor que fue creado.
* `docker ps -n 4` — Lista los últimos `N` contenedores creados (ejemplo: los primeros 4).

### Creación y Parada
```bash
docker run <nombre-imagen>   # Crea un contenedor usando el nombre o el ID de la imagen
docker stop <nombre-or-id>   # Detiene de forma segura un contenedor en ejecución
```

### Eliminación de Recursos
```bash
docker rm ubuntu2 ubuntu1    # Elimina uno o varios contenedores detenidos
docker rm -f apache          # Fuerza la eliminación de un contenedor (incluso si está encendido)
```

---

## Caso Práctico: Contenedor de Ubuntu

Puedes descargar y ejecutar una distribución de Ubuntu directamente con el comando `run`.

### 1. Creación básica (Segundo plano)
```bash
docker run --name ubuntu1 ubuntu
```

### 2. Creación Interactiva (Acceso inmediato)
Usa las banderas `-it` para interactuar directamente con la terminal del contenedor:
```bash
docker run --name ubuntu2 -it ubuntu
```

### 3. Reanimar y volver a entrar a un contenedor existente
Si el contenedor ya fue creado y se apagó, puedes encenderlo e ingresar a él mediante su intérprete de comandos (`bash` o `sh`):
```bash
docker start ubuntu2             # Levanta el contenedor apagado
docker exec -it ubuntu2 bash     # Entra de forma interactiva usando Bash
```
>  *Nota:* Si el contenedor no cuenta con `bash`, puedes acceder utilizando un intérprete más ligero como `sh`:
> ```bash
> docker exec -it apacheserver sh
> ```

---

##  Servidores Web y Mapeo de Puertos

### Modo Detached (`-d`)
Ejecuta el contenedor en segundo plano para liberar tu terminal y que no se quede bloqueada mostrando los procesos:
```bash
docker run --name apache -d 1b766f17b
```

### Publicación de Puertos (`-p`)
Vincula un puerto de tu computadora local con un puerto interno del contenedor (`puerto_local:puerto_contenedor`):
```bash
docker run --name apacheserver -d -p 81:80 httpd:alpine
```

---

##  Volúmenes (`-v`)
Los volúmenes sirven para persistir datos y enlazar carpetas de tu computadora real con directorios dentro del contenedor. Cualquier cambio en tu entorno local se verá reflejado inmediatamente en el contenedor.

```bash
docker run -d --name serverapache2 -p 8023:80 -v ./app:/usr/local/apache2/htdocs/app 1b766f
```
* **`-v`**: Bandera para inicializar un volumen.
* **`./app`**: Tu carpeta local (origen).
* **`/usr/local/...`**: La ruta interna del contenedor (destino).
