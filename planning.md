 
# Análisis de Requerimientos de Desarrollo de Proyectos

## Información General del Proyecto

**Nombre del Proyecto:** Station TV
**Cliente/Empresa:** Station
**Fecha de Inicio:** 21/10/2024
**Responsable del Proyecto:** Jorge Guerrero
**Equipo de Desarrollo:**
- Miguel Camarena - WEB Frontend/UX Design

- Diego Barajas - WEB Backend

- Jorge Guerrero - IoT Embebidos

  

## 1. Descripción del Proyecto
El proyecto *Station TV* consiste en el desarrollo de un sistema de gestión de contenido multimedia para reproducir listas de videos e imágenes en dispositivos Raspberry Pi ubicados en diferentes sucursales de la cadena Station. El sistema permitirá la gestión remota del contenido a través de un aplicativo web, facilitando la creación de listas de reproducción y la asignación de estas a grupos específicos de dispositivos.

  
## 2. Objetivos del Proyecto

-  **Objetivo General:**

Desarrollar un sistema integrado que permita la gestión y reproducción de contenido multimedia en las pantallas de sucursal de manera centralizada y remota, mejorando la experiencia visual y la eficiencia operativa de las sucursales.

-  **Objetivos Específicos:**

- Permitir la creación y gestión de listas de reproducción multimedia desde un aplicativo web.
- Facilitar la agrupación de dispositivos por ID de ubicación para asignarles contenido de manera organizada.
- Implementar una plataforma que permita el control y monitoreo en tiempo real del contenido reproducido en cada dispositivo.

  

## 3. Funcionalidades Incluidas
- Desarrollo de un aplicativo web para la creación y gestión de listas de reproducción multimedia.

- Implementación de funcionalidades para agrupar dispositivos por ID de ubicación.

- Control de orden de la reproduccion de contenido.

- Calendario y Agenda de reproducción de contenido.

- Control remoto del contenido reproducido en dispositivos Raspberry Pi.

- Montaje del aplicativo web en un servidor físico con NGINX para acceso público.

- Instalacion de certificados de seguridad para aplicativo web.

  

### 3.1 Funcionalidades Excluidas
- Integración con plataformas de terceros para la gestión de contenido.

- Compatibilidad con otros dispositivos que no sean Raspberry Pi.

- Desarrollo de aplicaciones móviles para gestión del contenido.

  

## 4. Requerimientos Funcionales

  
|  ID | Nombre | Descripción |
|--|--|--|
| RF01 | Inicio de Sesión | Inicio de sesión para acceder al sistema, solo usuarios "type": "admin/media" tendrán acceso |
| RF02 | Visualizar media | Ver la media cargada en mi región, zona o sucursal, con filtros y busqueda por titulo |
| RF03 | Agregar media | Almacenar nuevo archivo en la base de datos y servidor |
| RF04 | Editar media | Editar información de un registro de archivo |
| RF05 | Eliminar media | Eliminar un registro de archivo |
| RF06 | Crear región | Crear una nuevo registro de región [grupo de sucursales] en la base de datos y agrupar ciertas sucursales. (SOLO ADMINISTRADORES) |
| RF07 | Crear grupo | Crear una nuevo registro de zona [subgrupo de sucursales dentro de una región] en la base de datos y agrupar ciertas sucursales. (SOLO ADMINISTRADORES) |
| RF08 | Editar región | Modificar un registro de región en la base de datos y agrupar ciertas sucursales. (SOLO ADMINISTRADORES) |
| RF09 | Editar grupo | Modificar un registro de zona en la base de datos y agrupar ciertas sucursales. (SOLO ADMINISTRADORES) |
| RF10 | Eliminar región | Eliminar un registro de región en la base de datos y agrupar ciertas sucursales. (SOLO ADMINISTRADORES) |
| RF11 | Eliminar grupo | Eliminar un registro de región en la base de datos y agrupar ciertas sucursales. (SOLO ADMINISTRADORES) |
| RF12 | Crear lista de reproducción | Crear un listado con diferentes tipos de media, organizando el orden de reproducción |
| RF13 | Editar lista de reproducción | Modificar un listado con diferentes tipos de media, reorganizando el orden de reproducción, cambiando el nombre |
| RF14 | Eliminar lista de reproducción | Eliminar el registro de la lista de reproducción  |
| RF15 | Agregar sucursal | Añadir un registro nuevo de sucursal basado en el API de EVO. (SOLO ADMINISTRADORES) |
| RF16 | Agregar rango "media" en los usuarios | En el aplicativo "Access Controller" añadir el rango o tipo "media" para los usuarios |
| RF17 | API para enviar los medios | Un API que devuelva algun archivo o lista de reproducción para el uso en el Raspberry Pi |
| RF18 | Calendario para la gestión del contenido en función a una lista de reproducción |
| RF19 | Control remoto para controlar la reproducción en un Rasperri Pi |


### 4.1 Software

- Desarrollo del backend para la gestión de listas de reproducción y dispositivos (Diego Barajas).
- Desarrollo del frontend para la interfaz de usuario final y administrador web (Miguel Camarena).
- Implementación de APIs para la comunicación entre el servidor y los dispositivos embebidos.

  

### 4.2 Hardware / Sistemas Embebidos

  

- Configuración y programación de dispositivos Raspberry Pi 5.

- Implementación de software en Raspberry Pi para recibir, procesar y reproducir listas de contenido.

  

### 4.3 Plataformas Web / APIs

  

- Desarrollo del aplicativo web utilizando tecnologías...

  

### 4.4 Automatizaciones

  

- Sincronización automática de contenido multimedia desde el servidor a los dispositivos Raspberry Pi cada 10 minutos.

- Actualización en tiempo real de listas de reproducción asignadas a los dispositivos.

- Instalación automatica de dependencias de software y drivers requeridos.

- Actualización automatica del firmware necesario para funcionamiento de la solución.

  

## 5. Requerimientos No Funcionales

  

Aspectos de calidad y restricciones del sistema.

  

-  **Desempeño:**

El sistema debe poder actualizar y sincronizar contenido en dispositivos en menos de 2 minutos por operación de cambio de lista de reproducción.

  

-  **Seguridad:**
Uso de sesiones encriptadas con JWT y manejo de credenciales con permisos para cada petición al servidor backend, bloqueo de encabezados no necesarios para las peticiones.
Manejo de errores para cada petición y respuesta de API.
  

-  **Usabilidad:**

  

-  **Compatibilidad:**
PC:
	- Navegadores Chrome y Edge
	- Navegadores Firefox, Safari, Chromium (Puede tener ligeros errores)
  

## 6. Requerimientos de Infraestructura

  

-  **Servidor:**

El sistema se montará en un servidor físico on-premises utilizando NGINX para servir el aplicativo web.

  

-  **Bases de Datos:**
  
El sistema utilizará algunos modelos de base de datos ya existentes de los cuales el modelo "users" será ligeramente modificado para aceptar el key "type": "media", se agregarán algunos modelos nuevos (regiones, grupos, archivos, listas de reproducción) y se utilizará el almacenamiento del servidor para guardar los archivos subidos (por cuestiones de velocidad).
  

-  **Red y Conectividad:**
  
Para acceder al aplicativo se requiere de conexión a internet estable.
  

## 7. Cronograma de Desarrollo y Checkpoints

  

### 7.1 Fases del Proyecto


| Fase           | Descripción                            | Fecha de Inicio | Fecha de Fin |
| -------------- | -------------------------------------- | --------------- | ------------ |
| Planificación  | Definición de requisitos y funciones.  | 15/10/2024      | 22/10/2024   |
| Diseño   	 | Diseño de interfaces.      		  | 22/10/2024      | 26/10/2024   |
| Desarrollo   	 | Desarrollo de frontend y backend.      | 26/10/2024      | 10/11/2024   |
| Pruebas     	 | Pruebas de funcionalidad e integración | 10/11/2024      | 15/11/2024   |
| Implementación | Montaje en servidor y pruebas finales. | 10/11/2024      | 14/11/2024   |

  

### 7.2 Checkpoints de Avance
-  **Checkpoint 1:** Revisión de requerimientos y fases el proyecto (22/10/2024).

-  **Checkpoint 2:** Revisión del diseño de la arquitectura y del desarrollo inicial (26/10/2024).

-  **Checkpoint 3:** Prueba de funcionalidad y pruebas de carga en el servidor (04/11/2024).

-  **Checkpoint 4:** Implementación en producción y ajustes finales (15/11/2024).

-  **Cierre de Proyecto:** Revision de la solución integrada para su entrega y cierre de desarrollo del proyecto(15/11/2024).

  

## 8. Reuniones de Seguimiento

  

-  **Reunión Inicial:**

21/10/2024 - Definición de roles y responsabilidades.

  

-  **Reuniones Periódicas:**

Semanal, para seguimiento de avances y ajustes de cronograma.

  

-  **Reunión de Cierre:**

15/11/2024 - Revisión final y cierre del proyecto.

  

## 9. Riesgos y Contingencias

  

-  **Riesgo 1:**

Retrasos en la entrega de componentes de hardware. Plan: Establecer un stock de dispositivos de respaldo.


-  **Riesgo 2:**

Problemas de conectividad del servidor. Plan: Implementar redundancia en la conexión de red.


- **Riesgo 3:**

Retrasos en desarrollo por inconvenientes o complicaciones con la codificación. Plan: Acordar una junta para discutir el/los blockers y encontrar posibles soluciones.


- **Riesgo 4:**

Complicaciones y retrasos en la implementación. Plan: Acordar una junta para discutir el/los blockers y encontrar posibles soluciones.

## 10. Costos de diseño, desarrollo y despliegue 

### Diseño (Frontend) 
- Diseño UI/UX del aplicativo en figma - $3,000 MXN | Miguel Camarena
- Diseño responsivo del aplicativo para mobile - $1,500 MXN | Miguel Camarena

### Diseño (Backend) 
- Diseño de la arquitectura del backend, legible y con manejo de excepciones - $300 MXN | Diego Barajas
- Diseño y actualización de modelos de base de datos en MongoDB con mongoose - $300 MXN | Diego Barajas


### Desarrollo (Frontend) 
- Desarrollo frontend en ReactJS y Sass, incluyendo adaptabilidad a mobile - $4,800 MXN | Miguel Camarena


### Desarrollo (Backend) 
- Desarrollo de un backend en NodeJS, Express y Mongoose por medio de API para la comunicación cliente servidor - $7,000 MXN | Diego Barajas
- Conexión del frontend y backend por medio del API - $1,500 MXN | Diego Barajas


### Implementación en servidor
- Carga y configuración de aplicativo en el servidor - $350 MXN | Diego Barajas
- Configuración de mediador con servidor NGINX - $150 MXN | Diego Barajas


### Documentación
- Diagrama de arquitectura del sistema - $200
- Manual de usuario para la gestión de contenido en el aplicativo web - $300
- Especificaciones técnicas del montaje en RED y servidor NGINX - $300 MXN




## 11. Documentación Complementaria

- Diagrama de arquitectura del sistema.

- Manual de usuario para la gestión de contenido en el aplicativo web.

- Especificaciones técnicas del montaje en RED y servidor NGINX.


DOCUMENTO V1.0
