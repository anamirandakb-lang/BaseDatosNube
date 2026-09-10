# AWS Academy: Cloud Foundation

##  Información General
* **Programa:** Cloud Foundation (AWS Academy)
* **Estructura:** 3 Unidades académicas.
* **Proyecto Integrador:** `CampusCloud` (Se construirá progresivamente por etapas).
* **Entregable Final:** Constancia oficial del curso.

---

##  Tecnologías y Arquitectura del Proyecto
El proyecto `CampusCloud` integrará los siguientes componentes tecnológicos:

* **Nginx:** Utilizado como Proxy Inverso.
* **MinIO:** Almacenamiento de objetos (equivalente local a AWS S3).
* **Bases de Datos Relacionales:** SQL Server.
* **Bases de Datos NoSQL:** MongoDB (Documentos) y Cassandra / ScyllaDB (Columnas anchas).
* **Nube Académica:** Configuración de entornos locales mediante la administración de Docker (gestión de puertos, volúmenes, credenciales y optimización de equipos).

---

##  Plan de Estudios y Criterios de Evaluación

### 🔹 Unidad I: Base de Datos Relacionales en la Nube
* **Progreso del curso:** 20%
* **Flujo de trabajo:** `PC` ➡️ `Docker` ➡️ `SQL Server` ➡️ `CampusCloud`
* **Enfoque:** Comprender la teoría, implementar el entorno y gestionar los datos tabulares mediante el **Modelo Relacional** (tablas, llaves primarias/foráneas, índices, vistas, triggers).

####  Criterios de Evaluación (Unidad I)
* **20% — Matriz Comparativa:** Tabla comparativa entre AWS, Azure y Google Cloud (solución de servicios y responsabilidades administrativas).
* **50% — Implementación Relacional:** Configuración de SQL Server en Docker con persistencia de datos, despliegue de `CampusCloud`, operaciones CRUD, gestión de usuarios/privilegios y conexiones remotas.
* **30% — Reporte Integrador:** Documentación de arquitectura, procedimientos, consultas, pruebas, bitácora de problemas generados con sus respectivas soluciones y conclusiones de Cloud.

---

### 🔹 Unidad II: Base de Datos NoSQL en la Nube
* **Progreso del curso:** 60% (Acumulado)
* **Enfoque:** Análisis y explotación de modelos no tabulares:
  * **Documentos:** MongoDB
  * **Grafos:** Neo4j
  * **Columnas Anchas:** Cassandra o ScyllaDB
  * **Objetos:** Almacenamiento conceptual / MinIO

####  Criterios de Evaluación (Unidad II)
* **20% — Análisis y Selección:** Evaluación y justificación del modelo NoSQL ideal (grafos, documentos u objetos) según el caso de uso.
* **55% — Prácticas Integradas:** Portafolio compacto con las prácticas técnicas de NoSQL ejecutadas.
* **25% — Reporte Técnico Integrado:** Documentación de la entrega arquitectónica.

---

### 🔹 Unidad III: Integración de Aplicaciones y Base de Datos
* **Progreso del curso:** 100% (Cierre)
* **Enfoque:** Conectividad y consumo de servicios. 
  * **Conexiones:** Configuración de Host, IPs, puertos, credenciales y cadenas de conexión (*Connection Strings*).
  * **Endpoints:** Creación de rutas seguras para consultar y modificar información.
  * **Integración:** Consumo de mínimo dos servicios (al menos uno de ellos debe ser NoSQL).

####  Criterios de Evaluación (Unidad III)
* **30% — Conexión de Aplicación:** Enlace correcto entre el código de la app y las bases de datos.
* **30% — Consumo e Integración:** Flujo de datos funcional a través de los endpoints de servicios.
* **40% — Reporte + Demostración Final:** Exposición práctica del ecosistema completo en funcionamiento.

---

## Concepto Clave a Recordar
>  **ECS (Elastic Container Service):** Funciona conceptualmente como una máquina virtual de un pedazo de servidor; actúa como un repositorio estructurado donde podemos ir metiendo y gestionando nuestras cosas (contenedores) en la nube.
