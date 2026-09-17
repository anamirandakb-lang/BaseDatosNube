# Base de Datos en la Nube

**Fecha:** 17/09/2026


## Flujo Básico de una Consulta

1. **El cliente envía una petición o consulta** (por ejemplo, desde una aplicación móvil, interfaz web o cliente SQL).
2. **El servidor recibe la solicitud.**
3. **Busca o procesa la información** *(Backend / Motor de BD)*.
4. **Devuelve el resultado** al cliente *(Frontend / Interfaz)*.

> **Aclaración de roles:** El procesamiento de la consulta se realiza en el **backend** (servidor/motor de BD), mientras que el **frontend** recibe y presenta el resultado al usuario.


## Conceptos Clave de Redes

### Servidor de Nombres de Dominio (DNS)
Sistema que traduce nombres de dominio legibles por humanos (ej. `servidor-db-ejemplo.com`) a direcciones IP numéricas.

### Host, Localhost e IP

* **Host:** Nombre o ubicación de red a la que nos conectamos.
  * *Ejemplos:* `localhost`, `192.168.1.50`, `servidor-db-ejemplo.com`.
* **Localhost / 127.0.0.1:** Hace referencia a la **misma computadora** *(dirección de loopback)* donde se está ejecutando el programa.
* **IP (Internet Protocol):** Identificador único para un equipo o interfaz dentro de la red.
* **Analogía:** `Host / IP` equivale a la **dirección física** de un inmueble.

### Puerto
Define la ventana o servicio específico dentro de una computadora.

* **IP:** ¿A qué computadora nos conectamos?
* **Puerto:** ¿A qué servicio o aplicación dentro de esa computadora accedemos?
* **Sintaxis:** `IP:Puerto` (ej. `192.168.1.50:1433`)
  * `1433`: Puerto por defecto de **Microsoft SQL Server**.
  * `3306`: Puerto por defecto de **MySQL**.
  * `5432`: Puerto por defecto de **PostgreSQL**.
* **Analogía:** El `Puerto` equivale al **número de departamento o ventanilla** dentro de un edificio.


## Escenarios de Arquitectura

### 1. Escenario Local
Mi Computadora (Cliente SQL) -> SQL Server (Local) -> Base de Datos

### 2. Escenario Remoto (Red Local / LAN)
Mi PC Cliente -> Red Local -> Otra Computadora (Servidor SQL) -> Base de Datos

### 3. Escenario Cloud (Nube)
Cliente -> Internet / Red -> Proveedor Cloud -> Servicio Administrado de BD

#### Ejemplos de Servicios de BD Administrados en la Nube
* **AWS:** Amazon RDS, Amazon Aurora
* **Microsoft Azure:** Azure SQL Database
* **Google Cloud:** Cloud SQL

## ¿Dónde Vive mi Base de Datos?

* **Local:** `localhost` / `127.0.0.1`
* **Remoto:** `IP + Puerto` (red local empresarial o VPN)
* **Cloud:** Endpoint / URL administrada por el proveedor de nube


## Comparativo de Entornos

| Característica | Local | Remoto (LAN) | Cloud (Nube) |
| :--- | :--- | :--- | :--- |
| **Ubicación del Servidor** | Mi propia computadora | Otro equipo de la red local | Infraestructura del proveedor |
| **Acceso** | `localhost` / `127.0.0.1` | Dirección IP + Puerto | Endpoint vía Internet / VPN |
| **Administración** | 100% manual por el usuario | Manual por el equipo de TI | Administrado por el proveedor |
| **Mantenimiento** | Alto | Medio | Bajo (Respaldos y parches automáticos) |