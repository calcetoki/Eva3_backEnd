# API REST de Tareas

Esta API permite gestionar tareas (Crear, Listar, Detalle, Actualizar y Eliminar)
Contruida con **Django Rest Framework**

# RECURSOS y URIs

|      **Recurso**       |                           **Descripción**                              |
|------------------------|------------------------------------------------------------------------|
|   '/api/v1/tareas/'    | Lista todas las tareas o crea una nueva (GET, POST)                    |
| '/api/v1/tareas/{id}/' | Muestra, actualiza o elimina una tarea especifica (GET, PATCH, DELETE) |

# Verbos y Codigos Esperados

| **Metodo** |         **URI**        |             **Descripcion**             |   **Codigo de Respuesta**  | 
|------------|------------------------|-----------------------------------------|----------------------------|
| **GET**    |    '/api/v1/tareas/'   | Lista todas las tareas                  | '200 OK'                   |
| **POST**   |    '/api/v1/tareas/'   | Crea una nueva tarea                    | '201 Created'              |
| **GET**    | '/api/v1/tareas/{id}/' | Muestra el detalle de una tarea         | '200 OK' o '404 Not Found' |
| **PATCH**  | '/api/v1/tareas/{id}/' | Actualiza los campos 'titulo' o 'hecho' | '200 OK'                   |
| **DELETE** | '/api/v1/tareas/{id}/' | Elimina una tarea existente             | '204 No Content'           |

# Codigos Django

LOS CODIGOS SOLICITADOS ESTAN CONTENIDOS EN ESTE REPOSITORIO, ESPERO NO HABER OLVIDADO NINGUNO

INCLUIDOS: vistas, modelos, urls, validacion y transformacion(serializers), apps agregadas en settings .

# Diagrama de arquitectura

| Cliente (curl/SPA)              | Herramienta que consume la API (en mi caso Thunder CLient)      |
|---------------------------------|-----------------------------------------------------------------|
|
| HTTP/JSON                       | Protocolo y formato de comunicación entre cliente y servidor    |
|---------------------------------|-----------------------------------------------------------------|
|
| API /api/v1 (DRF ViewSets/URLs) | Capa que enruta las peticiones y las conecta con las vistas DRF |
|---------------------------------|-----------------------------------------------------------------|
|
| Logica/Serializers (validación) | Validan los datos y los transforman entre JSON y objetos Django |
|---------------------------------|-----------------------------------------------------------------|
|
| Modelo Django (ORM)             | Define la estructura de los datos y su relación con la BD       |
|---------------------------------|-----------------------------------------------------------------|
|
| DB SQLite (Local)               | Almacena de forma persistente (y local) las tareas creadas      |
|---------------------------------|-----------------------------------------------------------------|
