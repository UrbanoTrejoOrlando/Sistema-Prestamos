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

