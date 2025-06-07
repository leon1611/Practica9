
# Práctica #9 Creación de un entorno CRUD Mascotas con Docker Compose

## 1. Título

**Práctica No 9: Creación de un CRUD FullStack de Mascotas (React + Spring Boot + PostgreSQL + pgAdmin) utilizando Docker Compose**

## 2. Tiempo de duración

La duración estimada para esta práctica es de aproximadamente 1 a 2 horas.

## 3. Fundamentos

En esta práctica, se aplican los conocimientos de desarrollo fullstack y Docker para crear un sistema CRUD de Mascotas compuesto por un frontend en React, un backend en Spring Boot con Kotlin y una base de datos PostgreSQL, todo orquestado mediante Docker Compose. Adicionalmente, se incluye pgAdmin como herramienta de administración de la base de datos.

Docker Compose simplifica el levantamiento de múltiples servicios mediante un archivo `docker-compose.yml`, permitiendo definir redes, volúmenes y configuraciones de cada contenedor involucrado, logrando un entorno completamente aislado y reproducible.

## 4. Conocimientos previos

Docker permite crear contenedores para ejecutar aplicaciones de forma aislada, simplificando la configuración de entornos de desarrollo y despliegue (**Docker Documentation, 2025**). Docker Compose facilita la definición de entornos multi-contenedor mediante archivos YAML (**Docker Documentation, 2025**).

Spring Boot es un framework de desarrollo en Java/Kotlin que permite construir APIs REST de forma rápida (**Walls, 2016**), mientras que React permite construir interfaces de usuario interactivas en el navegador (**Griffiths, 2021**). PostgreSQL es un sistema de bases de datos relacional robusto y de código abierto (**PostgreSQL Documentation, 2025**). Finalmente, pgAdmin permite administrar de forma visual bases de datos PostgreSQL.

## 5. Objetivos a alcanzar

- Construir un archivo `docker-compose.yml` que integre los cuatro servicios.
- Implementar un backend REST con Spring Boot (Kotlin) para el manejo de mascotas.
- Construir un frontend en React con funcionalidad CRUD completa.
- Configurar pgAdmin para la administración de la base de datos.
- Definir redes y volúmenes Docker para la persistencia de datos y la comunicación entre servicios.

## 6. Equipo necesario

- Computador con sistema operativo **Windows 10 con WSL 2** (o equivalente con Docker Desktop instalado).
- Docker Desktop y WSL instalados y en ejecución.
- Editor de código (Visual Studio Code o similar).
- Conexión a Internet para descarga de imágenes Docker y dependencias.

## 7. Material de apoyo

- Documentación oficial de Docker, Spring Boot, React y PostgreSQL.
- Documentación de pgAdmin.
- Apuntes y ejemplos de clases.

## 8. Procedimiento

**Paso 1:** Crear la estructura de directorios del proyecto:

```
Otros/
├── mascota/          (Backend Spring Boot)
├── mascota-frontend/ (Frontend React)
└── docker-compose.yml
```

**Paso 2:** Desarrollar el backend con Spring Boot (Kotlin), implementando la entidad `Mascota` y los controladores REST para realizar las operaciones CRUD.

**Paso 3:** Desarrollar el frontend en React, diseñando la interfaz de usuario y conectándose al backend mediante fetch API, gestionando las operaciones de creación, edición, eliminación y listado de mascotas.

**Paso 4:** Crear el archivo `docker-compose.yml` para orquestar los servicios:

- Servicio `db` utilizando la imagen oficial de PostgreSQL.
- Servicio `pgadmin` para administración de la base de datos.
- Servicio `backend` con Spring Boot.
- Servicio `frontend` con React y Nginx para servir el build.

![alt text](<Screenshot 2025-06-07 180605.png>)

**Paso 5:** Configurar el backend para permitir CORS desde el frontend.

**Paso 6:** Construir los Dockerfile respectivos para backend y frontend, configurando correctamente los entornos.

**Paso 7:** Ejecutar `docker-compose up --build` para levantar el sistema completo.

**Paso 8:** Acceder al sistema CRUD desde el navegador:

- Frontend: `http://localhost:3000`
![alt text](<Screenshot 2025-06-07 180513.png>)
- Backend (API): `http://localhost:8080/api/mascotas`
![alt text](<Screenshot 2025-06-07 180720.png>)
- pgAdmin: `http://localhost:8081`
![alt text](<Screenshot 2025-06-07 180942.png>)


## 9. Resultados esperados

Al finalizar la práctica, se obtiene un entorno funcional de un CRUD de mascotas. El frontend permite registrar, editar, eliminar y visualizar mascotas, mientras que el backend gestiona las operaciones sobre la base de datos PostgreSQL. pgAdmin permite observar y administrar visualmente los registros almacenados.

El entorno se encuentra completamente dockerizado, permitiendo portabilidad, reproducibilidad y facilidad de despliegue.

## 10. Bibliografía

Docker Documentation. (2025). _Docker: Documentation_. https://docs.docker.com

Griffiths, A. (2021). _Learning React: Modern Patterns for Developing React Apps_. O'Reilly Media.

PostgreSQL Documentation. (2025). _PostgreSQL Official Documentation_. https://www.postgresql.org/docs/

Walls, C. (2016). _Spring Boot in Action_. Manning Publications.
