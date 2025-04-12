# Manual de Uso y Documentación Técnica - Microservicio de Investigadores

## Descripción General
Este microservicio forma parte del sistema de gestión académica de la Universidad Da Vinci. Su objetivo principal es permitir el registro, actualización, consulta y eliminación de investigadores dentro de la base de datos compartida del sistema.

---

## Tecnologías Utilizadas
- **Node.js**
- **Express.js**
- **MongoDB**
- **Mongoose**
- **Docker**

---

## Instalación y Ejecución del Microservicio

### 1. Clonar el repositorio
```bash
git clone <URL_DEL_REPOSITORIO>
cd microservicio-investigadores
```

### 2. Crear archivo `.env`
En la raíz del proyecto, crea un archivo `.env` con la siguiente línea:
```env
MONGO_URI=mongodb://mongodb_unico:27017/universidad
```

### 3. Ejecutar con Docker
```bash
docker-compose up --build
```

Asegúrate de haber creado la red externa previamente con:
```bash
docker network create red-microservicios
```

El microservicio estará disponible en:  
`http://localhost:5001`

---

## Endpoints Disponibles

| Método | Ruta                    | Descripción                             |
|--------|-------------------------|-----------------------------------------|
| GET    | /investigadores         | Obtener todos los investigadores        |
| GET    | /investigadores/:id     | Obtener un investigador por ID          |
| POST   | /investigadores         | Crear un nuevo investigador             |
| PUT    | /investigadores/:id     | Actualizar información de un investigador |
| DELETE | /investigadores/:id     | Eliminar un investigador                |

---

## Ejemplo de Objeto JSON para POST
```json
{
  "nombre": "Luis Pérez",
  "especialidad": "Biotecnología",
  "gradoAcademico": "Doctorado",
  "correo": "luis.perez@udv.edu.gt",
  "telefono": "22446688",
  "facultad": "Facultad de Ingeniería"
}
```

---

## Pruebas con Postman
Puedes importar los endpoints en Postman y probar las operaciones CRUD desde la interfaz.

1. Método: **POST**
2. URL: `http://localhost:5001/investigadores`
3. Body → raw → JSON

---

## Consideraciones de Seguridad
- Validaciones de datos en los modelos
- Control de errores con respuestas claras
- Uso de CORS habilitado para desarrollo

---

## Estructura del Proyecto
```
microservicio-investigadores/
├── models/
│   └── Investigador.js
├── routes/
│   └── investigadores.js
├── .env
├── Dockerfile
├── docker-compose.yml
├── server.js
└── README_investigadores.md
```

---

## Estado del Microservicio
El servicio está **funcional y desplegado correctamente** en su contenedor Docker. Se conecta a la base de datos MongoDB compartida (`mongodb_unico`) y expone sus rutas en el puerto `5001`.

---

## Autor
Rodrigo Avila 
202104215
Universidad Da Vinci

