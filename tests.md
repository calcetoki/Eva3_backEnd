		Listar
GET http://127.0.0.1:8000/api/v1/tareas/
STATUS: 200 OK

[
  {
    "id": 4,
    "titulo": "CuartaTarea",
    "hecho": false,
    "created_at": "2025-11-05T17:52:46.678094Z"
  },
  {
    "id": 3,
    "titulo": "SegundaTarea",
    "hecho": true,
    "created_at": "2025-11-05T03:05:03.369327Z"
  },
  {
    "id": 1,
    "titulo": "PrimeraTarea",
    "hecho": false,
    "created_at": "2025-11-05T02:33:12.493690Z"
  }
]

		Crear
POST http://127.0.0.1:8000/api/v1/tareas/
STATUS: 201 Created

{
  "id": 5,
  "titulo": "QuintaTarea",
  "hecho": false,
  "created_at": "2025-11-06T05:00:21.047208Z"
}

		Detalles
OPTIONS http://127.0.0.1:8000/api/v1/tareas/
STATUS: 200 OK

{
  "name": "Tarea List",
  "description": "",
  "renders": [
    "application/json",
    "text/html"
  ],
  "parses": [
    "application/json",
    "application/x-www-form-urlencoded",
    "multipart/form-data"
  ],
  "actions": {
    "POST": {
      "id": {
        "type": "integer",
        "required": false,
        "read_only": true,
        "label": "ID"
      },
      "titulo": {
        "type": "string",
        "required": true,
        "read_only": false,
        "label": "Titulo",
        "max_length": 100
      },
      "hecho": {
        "type": "boolean",
        "required": false,
        "read_only": false,
        "label": "Hecho"
      },
      "created_at": {
        "type": "datetime",
        "required": false,
        "read_only": true,
        "label": "Created at"
      }
    }
  }
}

		Editar
PATCH http://127.0.0.1:8000/api/v1/tareas/5/
STATUS: 200 OK

{
  "id": 5,
  "titulo": "QuintaTareaHecha",
  "hecho": true,
  "created_at": "2025-11-06T05:00:21.047208Z"
}

		Eliminar
DELETE http://127.0.0.1:8000/api/v1/tareas/3/
STATUS: 204 No Content
	     Listar_Nuevamente
GET http://127.0.0.1:8000/api/v1/tareas/

[
  {
    "id": 5,
    "titulo": "QuintaTareaHecha",
    "hecho": true,
    "created_at": "2025-11-06T05:00:21.047208Z"
  },
  {
    "id": 4,
    "titulo": "CuartaTarea",
    "hecho": false,
    "created_at": "2025-11-05T17:52:46.678094Z"
  },
  {
    "id": 1,
    "titulo": "PrimeraTarea",
    "hecho": false,
    "created_at": "2025-11-05T02:33:12.493690Z"
  }
]


 
