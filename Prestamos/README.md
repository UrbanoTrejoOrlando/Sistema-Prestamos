# API de Préstamos con Node.js, Express y MongoDB

Este proyecto implementa una **API RESTful para la gestión de préstamos de libros**, que permite realizar operaciones **CRUD (Crear, Leer, Actualizar y Eliminar)**.  
La API está desarrollada con **Node.js** y **Express**, y utiliza **MongoDB** como base de datos.  
Además, esta API se comunica con la **API de Usuarios y Libros**, permitiendo validar la disponibilidad de los libros y gestionar los préstamos de manera integral.

## 🛠 Tecnologías utilizadas

- Node.js  
- Express  
- MongoDB  
- Mongoose  
- dotenv (variables de entorno)  
- (Opcional) nodemon para desarrollo  

## Instalación

1.- Clonar el repositorio
```bash
 git clone https://github.com/UrbanoTrejoOrlando/Sistema-Prestamos.git
```
2.- Navegar al directorio del proyecto
```bash
cd Prestamos
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
| POST   | `/loans`     | Hacer un prestamo         |
| GET    | `/loans`     | Obtener todos los usuarios     |
| GET    | `/loans/:id` | Obtener un prestamo por el id |
| GET | `loans/user/:id` | Obtener los prestamos que tiene un usuario             |
| PUT | `/loans/:id` | Actualizar la devolucion de un libro             |
| DELETE | `/loans/:id` | Eliminar un prestamo             |

## Rutas disponibles 
### 🔸 Crear un prestamo (POST `/loans`)

- **URL:** `http://localhost:4001/loans`
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
- **URL:** `http://localhost:4001/loans`
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
- **URL:** `http://localhost:4001/loans/690d0d5276394bb2a253d0d3`
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
- **URL:** `http://localhost:4001/loans/user/690d0cd647d30ac60b4c4d0b`
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
- **URL:** `http://localhost:4001/loans/690d0d5276394bb2a253d0d3`
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
- **URL:** `http://localhost:4001/loans/690d0d5276394bb2a253d0d3`
- **Método:** DELETE
- **Respuesta esperada: 200 OK**
```json
{
    "message": "Préstamo eliminado"
}


