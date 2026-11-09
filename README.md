# TaskFlow

**Sistema web de gestión colaborativa de tareas**

## 1. Descripción del proyecto

TaskFlow es un proyecto académico orientado al desarrollo de una aplicación web que permitirá organizar, asignar y realizar seguimiento de tareas de manera colaborativa.

El proyecto se desarrolla como parte de la asignatura **Integración Continua**, utilizando herramientas de desarrollo de software, control de versiones y contenedorización.

## 2. Tecnologías del proyecto

| Tecnología | Función |
|---|---|
| Python 3.12 | Lenguaje de programación |
| Flask | Framework previsto para la aplicación web |
| PostgreSQL 16 | Sistema de gestión de base de datos |
| Docker | Ejecución de servicios en contenedores |
| Docker Compose | Configuración reproducible de los servicios |
| GitHub | Repositorio compartido y control de versiones |

## 3. Infraestructura Docker implementada

Se descargaron dos imágenes oficiales desde Docker Hub y se utilizaron para crear los siguientes contenedores:

| Contenedor | Imagen oficial | Función |
|---|---|---|
| `taskflow-db` | `postgres:16` | Servidor de base de datos PostgreSQL |
| `taskflow-web` | `python:3.12-slim` | Entorno Python para la futura aplicación web |

Ambos contenedores se encuentran conectados mediante una red Docker personalizada denominada `taskflow-net`.

Actualmente, el contenedor Python permanece activo como entorno de ejecución. La aplicación Flask todavía no está implementada.

## 4. Pruebas realizadas

Se realizaron las siguientes verificaciones:

- Descarga de las imágenes oficiales.
- Creación y ejecución simultánea de los dos contenedores.
- Creación de la red Docker `taskflow-net`.
- Incorporación de ambos contenedores a la red.
- Verificación del estado de PostgreSQL mediante `pg_isready`.
- Resolución del nombre `taskflow-db` desde Python.
- Conexión TCP exitosa desde Python al puerto 5432 de PostgreSQL.

Estas pruebas confirmaron la conectividad entre los contenedores. La integración de Flask con la base de datos queda pendiente para la siguiente etapa.

## 5. Reproducción de la infraestructura

El repositorio incluye el archivo `compose.yaml`, que permite reproducir la configuración inicial mediante Docker Compose.

**Requisitos:**

- Git.
- Docker con soporte para Compose.

**Procedimiento:**

1. Clonar el repositorio:

   `git clone https://github.com/LuisaGomez11/-TaskFlow.git`

2. Acceder a la carpeta del proyecto:

   `cd -TaskFlow`

3. Configurar una contraseña local para PostgreSQL. En PowerShell:

   `$env:POSTGRES_PASSWORD = "TU_CONTRASENA_SEGURA"`

4. Ejecutar los servicios:

   `docker compose up -d`

5. Verificar los contenedores:

   `docker compose ps`

**Nota:** La contraseña debe configurarse localmente y no debe publicarse en GitHub. Los nombres y puertos utilizados en Compose deben estar disponibles; si ya existen contenedores con los mismos nombres, es necesario resolver ese conflicto antes de ejecutarlo.

## 6. Organización y colaboración

GitHub se utiliza para compartir los archivos del proyecto, documentar la infraestructura y facilitar el trabajo colaborativo.

Las imágenes oficiales se obtienen desde Docker Hub. Los contenedores se ejecutan localmente en cada computador o en un servidor con Docker.

El archivo `compose.yaml` permite que los integrantes del equipo reproduzcan la configuración inicial sin crear manualmente cada contenedor.

## 7. Estado actual del proyecto

**Completado:**

- Repositorio GitHub creado.
- Imágenes oficiales descargadas.
- Dos contenedores Docker creados y funcionando localmente.
- Red compartida configurada.
- Comunicación TCP entre contenedores verificada.
- Archivo Docker Compose publicado.

**Pendiente:**

- Desarrollo de la aplicación web con Flask.
- Implementación de las funcionalidades de gestión de tareas.
- Conexión de la aplicación Flask con PostgreSQL.
- Pruebas de integración de la aplicación.
- Automatización del proceso de integración continua.

## 8. Contexto académico

**Proyecto:** TaskFlow  
**Asignatura:** Integración Continua  
**Modalidad:** Trabajo colaborativo  
**Propósito:** Aplicar herramientas de contenedorización, control de versiones e integración continua al desarrollo de una aplicación web.
