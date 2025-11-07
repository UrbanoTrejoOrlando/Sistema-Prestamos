# Sistema-Préstamos  
API de préstamos con usuarios, libros conectadas a un Api-Gateway  

## Descripción  
Este proyecto constituye un sistema de gestión de préstamos que consta de varios microservicios:  
- Un **API Gateway** que dirige las solicitudes a los distintos servicios.  
- Un servicio de **Usuarios y Libros** que gestiona la información básica de usuarios y libros.  
- Un servicio de **Préstamos** que gestiona las operaciones de préstamo (registro, devolución, historial).  

La arquitectura permite escalabilidad, separación de responsabilidades y despliegue independiente de cada servicio.

## Tecnologías utilizadas  
- JavaScript / Node.js.  
- Frameworks para construcciones de APIs (Express)  
- Base de datos (cada microservicio puede tener su propia base de datos: MongoDB
- Arquitectura de microservicios + API Gateway.

### 📁 Estructura del proyecto  

**Sistema-Prestamos**

- **Api-Gateway/** ← Microservicio Gateway (orquestador) 
- **Api-Usuarios-Libros/** ← Microservicio de usuarios y libros
- **Prestamos/** ← Microservicio de prestamos
- README.md ← Este README principal

---

## Cómo usar el proyecto

Se recomienda primero configurar y levantar **Api-Usuarios-Libros** y **Prestamos** para ejecutar **Api-Gateway**
### Api-Gateway*

- Documentación completa y pasos de instalación en:  
  [Api-Gateway/README.md](Api-Gateway/README.md)

### Api-Usuarios-Libros

- Documentación completa y pasos de instalación en:  
  [Api-Usuarios-Libros/README.md](Api-Usuarios-Libros/README.md)

### Prestamos

- Documentación completa y pasos de instalación en:  
  [Prestamos/README.md](Prestamos/README.md)

---
