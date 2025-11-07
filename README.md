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
- Frameworks para construcciones de APIs (por ejemplo Express u otro similar — ajustar según corresponda).  
- Base de datos (cada microservicio puede tener su propia base de datos; ajustar: MongoDB, PostgreSQL, etc).  
- Arquitectura de microservicios + API Gateway.
