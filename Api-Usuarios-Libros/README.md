# API de Usuarios y Libros con Node.js, Express y MongoDB

Este proyecto implementa una **API RESTful para la gestión de usuarios y libros**, que permite realizar operaciones **CRUD (Crear, Leer, Actualizar y Eliminar)**.  
La API está desarrollada con **Node.js** y **Express**, y utiliza **MongoDB** como base de datos.  
Además, esta API se comunica con otra API de libros, lo que permite manejar de forma integrada la información de usuarios y los préstamos de libros.

## 🛠 Tecnologías utilizadas

- Node.js  
- Express  
- MongoDB  
- Mongoose  
- dotenv (variables de entorno)  
- (Opcional) nodemon para desarrollo  

---

## Instalación

1.- Clonar el repositorio
```bash
 git clone https://github.com/UrbanoTrejoOrlando/Sistema-Prestamos.git
```
2.- Navegar al directorio del proyecto
```bash
cd Api-Usuarios-Libros
```
3.- Instala las dependencias
```bash
npm install
```
4.- Inicia el servidor
- En **modo desarrollo**
```bash
npm run dev
```
- En **modo producción**
```bash
npm start
```
## Rutas de la API

| Método | Ruta         | Descripción                    |
|--------|--------------|--------------------------------|
| POST   | `/users`     | Crear un nuevo usuario         |
| GET    | `/users`     | Obtener todos los usuarios     |
| GET    | `/users/:id` | Obtener un usuario por el id |
| PUT | `/users/:id` | Editar un usuario             |
| DELETE | `/users/:id` | Eliminar un usuario             |
| POST   | `/books`     | Crear un nuevo libro         |
| GET    | `/books`     | Obtener todos los libros    |
| GET    | `/books/:id` | Obtener un libro por el id |
| PUT | `/books/:id` | Editar un libro            |
| DELETE | `/books/:id` | Eliminar un libro             |


## Rutas disponibles (Usuarios)
### 🔸 Crear un nuevo usuario (POST `/users`)

- **URL:** `http://localhost:4000/api/users/`
- **Método:** POST
- **Body (JSON):**

```json
{
    "nombre": "ernesto",
    "email": "ernesto@gmail.com",
    "password": "dulce",
    "rol": "usuario",
    "edad": 26,
    "direccion": "Mexico"
}

```
- **Respuesta esperada: 201 Created**
```json
{
    "message": "Usuario creado exitosamente",
    "user": {
        "nombre": "ernesto",
        "email": "ernesto@gmail.com",
        "password": "$2b$10$lF0n03NxTkp/7WP37UfAOOIJgx.JQGszNhW2e2t7/xxE9P0ypKTLy",
        "rol": "usuario",
        "edad": 26,
        "direccion": "Mexico",
        "_id": "690cdfb347d30ac60b4c4cfe",
        "createdAt": "2025-11-06T17:49:39.821Z",
        "updatedAt": "2025-11-06T17:49:39.821Z",
        "__v": 0
    }
}

```
### 🔸 Obtener todos los usuarios (GET `/users`)
- **URL:** `http://localhost:4000/api/users/`
- **Método:** GET
- **Respuesta esperada: 200 OK**
```json
[
    {
        "_id": "690cdfb347d30ac60b4c4cfe",
        "nombre": "ernesto",
        "email": "ernesto@gmail.com",
        "password": "$2b$10$lF0n03NxTkp/7WP37UfAOOIJgx.JQGszNhW2e2t7/xxE9P0ypKTLy",
        "rol": "usuario",
        "edad": 26,
        "direccion": "Mexico",
        "createdAt": "2025-11-06T17:49:39.821Z",
        "updatedAt": "2025-11-06T17:49:39.821Z",
        "__v": 0
    }
]
```

### 🔸 Obtener un usuario por el id (GET `/users/:id`)
- **URL:** `http://localhost:4000/api/users/690cdfb347d30ac60b4c4cfe`
- **Método:** GET
- **Respuesta esperada: 200 OK**
```json
[
    {
        "_id": "690cdfb347d30ac60b4c4cfe",
        "nombre": "ernesto",
        "email": "ernesto@gmail.com",
        "password": "$2b$10$lF0n03NxTkp/7WP37UfAOOIJgx.JQGszNhW2e2t7/xxE9P0ypKTLy",
        "rol": "usuario",
        "edad": 26,
        "direccion": "Mexico",
        "createdAt": "2025-11-06T17:49:39.821Z",
        "updatedAt": "2025-11-06T17:49:39.821Z",
        "__v": 0
    }
]
```
### 🔸 Actualizar un usuario (PUT `/users/:id`)
- **URL:** `http://localhost:4000/api/users/690cdfb347d30ac60b4c4cfe`
**Método:** PUT
- **Body (JSON):**
```json
{
    "email": "starlord@gmail.com"
}
```
- **Respuesta esperada: 200 OK**
```json
{
    "message": "Usuario actualizado exitosamente",
    "user": {
        "_id": "690cdfb347d30ac60b4c4cfe",
        "nombre": "ernesto",
        "email": "starlord@gmail.com",
        "password": "$2b$10$lF0n03NxTkp/7WP37UfAOOIJgx.JQGszNhW2e2t7/xxE9P0ypKTLy",
        "rol": "usuario",
        "edad": 26,
        "direccion": "Mexico",
        "createdAt": "2025-11-06T17:49:39.821Z",
        "updatedAt": "2025-11-06T18:00:58.307Z",
        "__v": 0
    }
}
```
### 🔸 Eliminar una tarea (DELETE `/users/:id`)
- **URL:** `http://localhost:4000/api/users/690cdfb347d30ac60b4c4cfe`
**Método:** DELETE
- **Respuesta esperada: 200 OK**
```json
{
    "message": "Usuario eliminado exitosamente",
    "user": {
        "_id": "690cdfb347d30ac60b4c4cfe",
        "nombre": "ernesto",
        "email": "starlord@gmail.com",
        "password": "$2b$10$lF0n03NxTkp/7WP37UfAOOIJgx.JQGszNhW2e2t7/xxE9P0ypKTLy",
        "rol": "usuario",
        "edad": 26,
        "direccion": "Mexico",
        "createdAt": "2025-11-06T17:49:39.821Z",
        "updatedAt": "2025-11-06T18:00:58.307Z",
        "__v": 0
    }
}
```

## Rutas disponibles (Libros)
### 🔸 Crear un nuevo libro (POST `/books`)

- **URL:** `http://localhost:4000/api/books/`
- **Método:** POST
- **Body (JSON):**
```json
{
    "titulo": "Viaje a las Estrellas",
    "autor": "Isaac Clarke",
    "ISBN": "978-0-12-345678-9",
    "fechaPublicacion": "2018-06-15",
    "genero": "Ciencia Ficción"
}

```
- **Respuesta esperada: 201 Created**
```json
{
    "message": "Libro creado exitosamente",
    "book": {
        "titulo": "Viaje a las Estrellas",
        "autor": "Isaac Clarke",
        "disponible": true,
        "ISBN": "978-0-12-345678-9",
        "fechaPublicacion": "2018-06-15T00:00:00.000Z",
        "genero": "Ciencia Ficción",
        "_id": "690ce5ae47d30ac60b4c4d04",
        "createdAt": "2025-11-06T18:15:10.893Z",
        "updatedAt": "2025-11-06T18:15:10.893Z",
        "__v": 0
    }
}
```

### 🔸 Obtener todos los libros (GET `/books`)
- **URL:** `http://localhost:4000/api/books/`
- **Método:** GET
- **Respuesta esperada: 200 OK**
```json
[
    {
        "_id": "690ce5ae47d30ac60b4c4d04",
        "titulo": "Viaje a las Estrellas",
        "autor": "Isaac Clarke",
        "disponible": true,
        "ISBN": "978-0-12-345678-9",
        "fechaPublicacion": "2018-06-15T00:00:00.000Z",
        "genero": "Ciencia Ficción",
        "createdAt": "2025-11-06T18:15:10.893Z",
        "updatedAt": "2025-11-06T18:15:10.893Z",
        "__v": 0
    }
]
```
### 🔸 Obtener un libro por el id (GET `/books/:id`)
- **URL:** `http://localhost:4000/api/books/690ce5ae47d30ac60b4c4d04`
- **Método:** GET
- **Respuesta esperada: 200 OK**
```json
{
    "_id": "690ce5ae47d30ac60b4c4d04",
    "titulo": "Viaje a las Estrellas",
    "autor": "Isaac Clarke",
    "disponible": true,
    "ISBN": "978-0-12-345678-9",
    "fechaPublicacion": "2018-06-15T00:00:00.000Z",
    "genero": "Ciencia Ficción",
    "createdAt": "2025-11-06T18:15:10.893Z",
    "updatedAt": "2025-11-06T18:15:10.893Z",
    "__v": 0
}
```

### 🔸 Actualizar un libro (PUT `/books/:id`)
- **URL:** `http://localhost:4000/api/books/690ce5ae47d30ac60b4c4d04`
**Método:** PUT
- **Body (JSON):**
```json
{
    "autor": "Autor desconocido"
}
```
- **Respuesta esperada: 200 OK**
```json
{
    "message": "Libro actualizado exitosamente",
    "book": {
        "_id": "690ce5ae47d30ac60b4c4d04",
        "titulo": "Viaje a las Estrellas",
        "autor": "Autor desconocido",
        "disponible": true,
        "ISBN": "978-0-12-345678-9",
        "fechaPublicacion": "2018-06-15T00:00:00.000Z",
        "genero": "Ciencia Ficción",
        "createdAt": "2025-11-06T18:15:10.893Z",
        "updatedAt": "2025-11-06T18:19:58.845Z",
        "__v": 0
    }
}
```

### 🔸 Eliminar un libro (DELETE `/books/:id`)
- **URL:** `http://localhost:4000/api/books/690ce5ae47d30ac60b4c4d04`
**Método:** DELETE
- **Respuesta esperada: 200 OK**
```json
{
    "message": "Libro eliminado exitosamente",
    "book": {
        "_id": "690ce5ae47d30ac60b4c4d04",
        "titulo": "Viaje a las Estrellas",
        "autor": "Autor desconocido",
        "disponible": true,
        "ISBN": "978-0-12-345678-9",
        "fechaPublicacion": "2018-06-15T00:00:00.000Z",
        "genero": "Ciencia Ficción",
        "createdAt": "2025-11-06T18:15:10.893Z",
        "updatedAt": "2025-11-06T18:19:58.845Z",
        "__v": 0
    }
}
```
