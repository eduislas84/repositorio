# Design Document: API REST CONTACTOS

## 1. Descripción
Ejemplo de una API REST para gestionar contactos  en una DB utilizando FastAPI

## 2. Objetivo
Realizar un ejemplo de diseño de una API REST de tipo CRUD y su posterior codificacion utilizando el framework [FastAPI](https://fastapi.tiangolo.com/).

## 3. Diseño de la BD
Para este ejemplo se utilizara el gestor de bases de datos [SQLite3](https://www.sqlite.org/index.html) con las siguientes tablas:

### 3.1 Tabla: contactos
|No.|Campo|Tipo|Restricciones|Descripcion|
|--|--|--|--|--|
|1|id_contactos|int|PRIMARY key|Llave primaria de la tabla|
|2|nombre|varchar|100|Tipo texto|
|3|primer_apelLido|varchar|50|Tipo Texto|
|4|segundo_apellido|varchar|50|Tipo texto|
|5|email|varchar|50|Tipo Texto|
|6|telefono|varchar|13|Tipo Texto|

## 3.2 Script
'''sql
CREATE TABLE contactos (
    id_contacto INT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    primer_apellido VARCHAR(50) NOT NULL,
    segundo_apellido VARCHAR(50) NOT NULL,
    email VARCHAR(50) NOT NULL,
    telefono VARCHAR(13) NOT NULL
);