# API-GATEWAY
Api gateway conbinando tres apis de usuarios, libros y prestamos.

**Nota:** Es importante tener en ejecución **Api_Usuario-Libros** y **Prestamos** 

## Instalación

1.- Clonar el repositorio
```bash
 git clone https://github.com/UrbanoTrejoOrlando/Sistema-Prestamos.git
```
2.- Navegar al directorio del proyecto
```bash
cd Api-Gateway
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

| Método | Ruta | Descripción |
|--------|------|-------------|
| <div align="center">🟩 **API-USUARIOS-LIBROS**</div> |  |  |
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
| <div align="center">🟦 **API-PRESTAMOS**</div> |  |  |
| POST   | `/loans`     | Hacer un prestamo         |
| GET    | `/loans`     | Obtener todos los usuarios     |
| GET    | `/loans/:id` | Obtener un prestamo por el id |
| GET | `/loans/user/:id` | Obtener los prestamos que tiene un usuario             |
| PUT | `/loans/:id` | Actualizar la devolucion de un libro             |
| DELETE | `/loans/:id` | Eliminar un prestamo             |

## Rutas disponibles (Api-Usuarios)
### 🔸 Crear un nuevo usuario (POST `/users`)

- **URL:** `http://localhost:4004/api1/api/users/`
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
- **URL:** `http://localhost:4004/api1/api/users/`
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
- **URL:** `http://localhost:4004/api1/api/users/690cdfb347d30ac60b4c4cfe`
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
- **URL:** `http://localhost:4004/api1/api/users/690cdfb347d30ac60b4c4cfe`
- **Método:** PUT
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
- **URL:** `http://localhost:4004/api1/api/users/690cdfb347d30ac60b4c4cfe`
- **Método:** DELETE
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
## Rutas disponibles (Api-Libros)
### 🔸 Crear un nuevo libro (POST `/books`)

- **URL:** `http://localhost:4004/api2/api/books`
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
- **URL:** `http://localhost:4004/api2/api/books`
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
- **URL:** `http://localhost:4004/api2/api/books/690ce5ae47d30ac60b4c4d0`
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
- **URL:** `http://localhost:4004/api2/api/books/690ce5ae47d30ac60b4c4d04`
- **Método:** PUT
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
- **URL:** `http://localhost:4004/api2/api/books/690ce5ae47d30ac60b4c4d04`
- **Método:** DELETE
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
## Rutas disponibles (Api-Prestamos)
### 🔸 Crear un prestamo (POST `/loans`)

- **URL:** `http://localhost:4004/api3/loans/`
- **Método:** POST
- **Body (JSON):**

```json
{
  "userId": "690d0cd647d30ac60b4c4d0b",
  "bookId": "690d0cda47d30ac60b4c4d0d",
  "loanDate": "2025-03-18",
  "returnDate": "2025-04-20"
}

```
- **Respuesta esperada: 201 Created**
```json
{
    "userId": "690d0cd647d30ac60b4c4d0b",
    "bookId": "690d0cda47d30ac60b4c4d0d",
    "returned": false,
    "_id": "690d0d5276394bb2a253d0d3",
    "loanDate": "2025-11-06T21:04:18.980Z",
    "__v": 0
}
```
### 🔸 Obtener todos los prestamos (GET `/loans`)
- **URL:** `http://localhost:4004/api3/loans/`
- **Método:** GET
- **Respuesta esperada: 200 OK**
```json
[
    {
        "_id": "690d0d5276394bb2a253d0d3",
        "userId": "690d0cd647d30ac60b4c4d0b",
        "bookId": "690d0cda47d30ac60b4c4d0d",
        "returned": false,
        "loanDate": "2025-11-06T21:04:18.980Z",
        "__v": 0
    }
]
```

### 🔸 Obtener un usuario por el id (GET `/loans/:id`)
- **URL:** `http://localhost:4004/api3/loans/690d0d5276394bb2a253d0d3`
- **Método:** GET
- **Respuesta esperada: 200 OK**
```json
{
    "_id": "690d0d5276394bb2a253d0d3",
    "userId": "690d0cd647d30ac60b4c4d0b",
    "bookId": "690d0cda47d30ac60b4c4d0d",
    "returned": false,
    "loanDate": "2025-11-06T21:04:18.980Z",
    "__v": 0
}
```
### 🔸 Obtener un usuario por el id (GET `/loans/user/:id`)
- **URL:** `http://localhost:4004/api3/loans/user/690d0cd647d30ac60b4c4d0b`
- **Método:** GET
- **Respuesta esperada: 200 OK**
```json
[
    {
        "_id": "690d0d5276394bb2a253d0d3",
        "userId": "690d0cd647d30ac60b4c4d0b",
        "bookId": "690d0cda47d30ac60b4c4d0d",
        "returned": false,
        "loanDate": "2025-11-06T21:04:18.980Z",
        "__v": 0
    }
]
```
### 🔸 Actualizar un prestamo por el id (PUT `/loans/:id`)
- **URL:** `http://localhost:4004/api3/loans/690d0d5276394bb2a253d0d3`
- **Método:** PUT
- **Body (JSON):**
```json
{
    "returnDate": "2025-05-20"
}
```
- **Respuesta esperada: 200 OK**
```json
{
    "_id": "690d0d5276394bb2a253d0d3",
    "userId": "690d0cd647d30ac60b4c4d0b",
    "bookId": "690d0cda47d30ac60b4c4d0d",
    "returned": false,
    "loanDate": "2025-11-06T21:04:18.980Z",
    "__v": 0,
    "returnDate": "2025-05-20T00:00:00.000Z"
}
```
### 🔸 Eliminar un prestamo (DELETE `/loans/:id`)
- **URL:** `http://localhost:4004/api3/loans/690d0d5276394bb2a253d0d3`
- **Método:** DELETE
- **Respuesta esperada: 200 OK**
```json
{
    "message": "Préstamo eliminado"
}
