# ForumHub

ForumHub es una API RESTful desarrollada con **Spring Boot**, diseñada para gestionar tópicos de discusión. Incluye autenticación mediante **JWT (JSON Web Token)** para proteger las solicitudes y funcionalidades avanzadas para la gestión de usuarios y temas.

## Características

- Autenticación segura con **JWT**.
- Operaciones CRUD para gestionar tópicos.
- Validación de datos en las solicitudes.
- Configuración de seguridad con **Spring Security**.
- Manejo de excepciones globales.
- Estructura modular para fácil mantenimiento.

---

## Requisitos Previos

Asegúrate de tener instalados los siguientes componentes:

- **Java 17** o superior
- **Maven** 3.6 o superior
- **PostgreSQL** (o cualquier base de datos compatible)
- **Postman** o **Insomnia** (para probar la API)

---

## Instalación

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/tu-usuario/forumhub.git
   cd forumhub
   ```

2. **Configurar la base de datos:**

   - Crea una base de datos en tu gestor (ejemplo: `forumhub`).
   - Configura las credenciales en `src/main/resources/application.properties`:
     ```properties
     spring.datasource.url=jdbc:postgresql://localhost:5432/forumhub
     spring.datasource.username=tu_usuario
     spring.datasource.password=tu_contraseña
     ```

3. **Construir el proyecto:**
   ```bash
   mvn clean install
   ```

4. **Ejecutar la aplicación:**
   ```bash
   mvn spring-boot:run
   ```

---

## Endpoints Principales

### **Autenticación**

- **POST** `/login`  
  Autentica a un usuario y devuelve un token JWT.
  ```json
  {
    "username": "admin",
    "password": "admin123"
  }
  ```

### **Tópicos**

- **GET** `/topics`  
  Devuelve la lista de tópicos disponibles.  
  **Headers:**  
  `Authorization: Bearer <JWT_TOKEN>`

- **POST** `/topics`  
  Crea un nuevo tópico.  
  **Body:**
  ```json
  {
    "title": "Nuevo Tópico",
    "content": "Contenido del tópico"
  }
  ```

- **PUT** `/topics/{id}`  
  Actualiza un tópico existente.

- **DELETE** `/topics/{id}`  
  Elimina un tópico por su ID.

---

## Estructura del Proyecto

```plaintext
forumhub/
├── config/            # Configuración de seguridad y JWT
├── controller/        # Controladores REST
├── dto/               # Clases para las solicitudes y respuestas
├── model/             # Entidades de la base de datos
├── repository/        # Interfaces de JPA para acceso a datos
├── service/           # Lógica de negocio
├── resources/         
│   ├── application.properties  # Configuración principal
│   ├── schema.sql      # Esquema de la base de datos
│   └── data.sql        # Datos iniciales
└── test/              # Pruebas unitarias
```

---

## Tecnologías Utilizadas

- **Java 17**
- **Spring Boot 3**
- **Spring Security**
- **JWT**
- **Maven**
- **H2 Database** (para pruebas)
- **PostgreSQL** (producción)

---

## Próximos Pasos

- Agregar soporte para roles de usuario (admin, user).
- Implementar paginación en la lista de tópicos.
- Mejorar el manejo de errores.

---

## Contribuciones

¡Las contribuciones son bienvenidas! Por favor, sigue estos pasos:

1. Haz un fork del repositorio.
2. Crea una rama nueva (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz commit (`git commit -m "Añadida nueva funcionalidad"`).
4. Envía un pull request.

---

## Licencia

Este proyecto está bajo la licencia **MIT**. Puedes consultar más detalles en el archivo [LICENSE](LICENSE).

---

## Contacto

- Autor: Marco Antonio Munguia Hernandez  
- Email: munguia_marco.104@outlook.com
