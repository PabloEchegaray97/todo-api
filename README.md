# API de Administración de Tareas

API RESTful para administrar tareas, organizarlas en Sprints y mantener un Backlog general.

## Tecnologías Utilizadas

- Node.js
- Express
- MongoDB
- Mongoose
- Express Validator
- Swagger para documentación

## Instalación

1. Clonar el repositorio:
```bash
git clone <url-del-repositorio>
cd todo-api
```

2. Instalar dependencias:
```bash
npm install
```

3. Configurar variables de entorno:
Crear un archivo `.env` en la raíz del proyecto con las siguientes variables:
```
PORT=3000
MONGODB_URI=mongodb://localhost:27017/todo-api
NODE_ENV=development
```

4. Iniciar el servidor:
```bash
npm run dev
```

5. Acceder a la documentación de Swagger:
```
http://localhost:3000/api-docs
```

## Estructura del Proyecto

```
/todo-api
├── models/       # Modelos de datos (Mongoose)
├── routes/       # Rutas de la API
├── controllers/  # Controladores
├── swagger.js    # Configuración de Swagger
├── app.js        # Archivo principal de la aplicación
└── .env          # Variables de entorno
```

## Endpoints

### Tareas
- `GET /api/tasks`: Obtener todas las tareas
- `GET /api/tasks/:id`: Obtener una tarea por ID
- `POST /api/tasks`: Crear una tarea
- `PUT /api/tasks/:id`: Editar una tarea
- `DELETE /api/tasks/:id`: Eliminar una tarea

### Sprints
- `GET /api/sprints`: Obtener todos los sprints
- `GET /api/sprints/:id`: Obtener un sprint por ID
- `POST /api/sprints`: Crear un sprint
- `PUT /api/sprints/:id`: Editar un sprint
- `DELETE /api/sprints/:id`: Eliminar un sprint
- `PUT /api/sprints/:id/add-task/:taskId`: Agregar una tarea a un sprint

### Backlog
- `GET /api/backlog`: Obtener el backlog
- `POST /api/backlog`: Crear backlog (solo uno)
- `PUT /api/backlog/add-task/:taskId`: Agregar una tarea al backlog

## Funcionalidades Adicionales

- Filtrado de tareas por estado: `GET /api/tasks?estado=pendiente`
- Ordenación de tareas por fecha límite: `GET /api/tasks?ordenarPorFecha=true`
- Validaciones en todas las operaciones
- Interfaz de Swagger para probar los endpoints: `http://localhost:3000/api-docs` 