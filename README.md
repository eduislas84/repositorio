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

## 3.3 Tabla: GET
|No.|Propiedad|Detalle|
|--|--|--|
|1|Descripcion|Endpoint raiz de la API|
|2|Summary|Endpoint raiz|
|3|Method|GET|
|4|Endpoint|http://localhost:8000/|
|5|QuerryParam|NA|
|6|PathParam|NA|
|7|Data|NA|
|8|Version|V1|
|9|Status Code|200 ok|
|10|Response Type|aplicacion/Json|
|11|Response||
|12|curl|curl<'Get''http://localhost:8000/'-H'accept:aplication/Json'|
|13|Status Code|NA|
|14|Responsable Type|NA|
|15|Response|NA|

## 3.4 Tabla: PAST
|No.|Propiedad|Detalle|
|--|--|--|
|1|Descripcion|Endpoint para enviar datos a la API|
|2|Summary|Endpoint para enviar datos|
|3|Method|POST|
|4|Endpoint|http://localhost:8000/|
|5|QuerryParam|NA|
|6|PathParam|NA|
|7|Data|Datos que se enviaron al servidor en el cuerpo de la solicitud|
|8|Version|V1|
|9|Status Code|201 Created|
|10|Response Type|aplicacion/Json|
|11|Response|{"Version":"V1":"message":"Datos recibidos correctamente":"datatime":"27/09/23:17:21"}|
|12|curl|curl-X'PAST''http://localhost:8000/'-H'accept:aplication/Json'-d'{"data":"ejemplo"}'|
|13|Status Code|400 Bad Request|
|14|Responsable Type|aplicacion/Json|
|15|Response|{"error":"Mensaje de error detallado"}|
