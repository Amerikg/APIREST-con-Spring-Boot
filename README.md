
# API REST con Spring Boot y MySQL

## Descripción

Este proyecto es una API RESTful creada con **Spring Boot** que interactúa con una base de datos **MySQL**. La API permite realizar operaciones CRUD sobre una entidad llamada `Person`, que tiene los campos `id`, `name`, `username` y `date_registry`. La aplicación es compatible con el control de concurrencia optimista utilizando el campo `@Version`.

## Tecnologías utilizadas

- **Spring Boot**: Framework para desarrollo de aplicaciones backend.
- **Spring Data JPA**: Para manejar la interacción con la base de datos utilizando JPA.
- **MySQL**: Sistema de gestión de bases de datos.
- **Postman**: Para realizar pruebas de la API.


## Requisitos

Para ejecutar este proyecto, asegúrate de tener los siguientes elementos
### Clonando el repositorio

```bash
git clone https://github.com/Amerikg/APIREST-con-Spring-Boot.git
```

### Configuración de MySQL

1. **Crear la base de datos:**

   Si aún no tienes una base de datos, puedes crearla manualmente en MySQL con el siguiente comando:

   ```sql
   CREATE DATABASE nombre_de_la_base_de_datos;
   ```

2. **Configurar las credenciales de la base de datos** en el archivo `application.properties` (en la carpeta `src/main/resources`):

   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/nombre_de_la_base_de_datos
   spring.datasource.username=tu_usuario
   spring.datasource.password=tu_contraseña
   spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
   ```

### Ejecutar el proyecto

1. **Compila y ejecuta la aplicación:**

   Si usas Maven:

   ```bash
   mvn clean spring-boot:run
   ```

   Si usas Gradle:

   ```bash
   gradle bootRun
   ```

2. **Accede a la API:**

   La API debería estar disponible en `http://localhost:8080/` por defecto.

## Endpoints

### 1. Obtener todas las personas (GET)

**URL**: `/api/persons`  
**Método**: GET

Devuelve una lista de todas las personas almacenadas en la base de datos.

### 2. Obtener una persona por ID (GET)

**URL**: `/api/persons/{id}`  
**Método**: GET

Devuelve una persona específica por su `id`.

### 3. Crear una persona (POST)

**URL**: `/api/persons`  
**Método**: POST

Crea una nueva persona. En el cuerpo de la solicitud, debes enviar los datos en formato JSON.

**Ejemplo de JSON**:

```json
{
    "name": "Juan Pérez",
    "userName": "jperez",
    "date": "2025-04-03"
}
```

### 4. Actualizar una persona (PUT)

**URL**: `/api/persons/{id}`  
**Método**: PUT

Actualiza los detalles de una persona existente.

**Ejemplo de JSON**:

```json
{
    "name": "Juan Pérez",
    "userName": "juanperez",
    "date": "2025-04-03"
}
```

### 5. Eliminar una persona (DELETE)

**URL**: `/api/persons/{id}`  
**Método**: DELETE

Elimina una persona específica por su `id`.

## Pruebas

Para realizar pruebas de la API, puedes usar **Postman** o cualquier herramienta similar para realizar solicitudes HTTP. Asegúrate de que el servidor de la API esté en funcionamiento antes de hacer las pruebas.
