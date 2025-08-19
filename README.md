# FOROHUB
🧠 ForoConnect API

Servicio REST creado con Spring Boot 3, orientado a la administración confiable y documentada de debates en un foro técnico. Incorpora autenticación mediante JWT, control detallado de accesos por perfiles y documentación interactiva con Swagger UI. Ideal para proyectos académicos o empresariales donde la seguridad y la transparencia son fundamentales.

🔐 Autenticación y Protección con JWT

La aplicación implementa un ciclo completo de autenticación con JSON Web Tokens (JWT), asegurando que solo usuarios autorizados accedan a los recursos del backend:

🔄 Proceso de autenticación

Ingreso del usuario (POST /auth/login): Se envían credenciales correctas (correo y clave).

Emisión del token JWT: Si los datos son válidos, el sistema devuelve un token firmado.

Acceso a recursos privados: El token debe incluirse en cada petición dentro del encabezado Authorization: Bearer <token>.

Control por perfil: Algunos endpoints exigen permisos concretos (ej. administrador, usuario estándar).

🔍 Validaciones automáticas

Tokens vencidos o corruptos devuelven 401 Unauthorized.

Intentos de acceso sin autorización suficiente responden con 403 Forbidden.

Un token válido habilita operaciones como crear, listar o responder temas del foro.

📘 Documentación con Swagger UI

Se integró Swagger/OpenAPI v3 para generar especificaciones técnicas y permitir pruebas en tiempo real desde el navegador:

Acceso: /swagger-ui/index.html

Soporta autenticación directa desde Swagger

Permite ejecutar endpoints protegidos con el token JWT

Muestra esquemas de datos, parámetros requeridos y ejemplos de respuesta

🧩 Endpoints disponibles
Endpoint	Método	Seguridad	Descripción
/auth/login	POST	Público	Inicio de sesión
/topicos	GET	Protegido	Obtener listado de debates
/topicos	POST	Protegido	Registrar un nuevo tema
/respuestas/{id}	POST	Protegido	Responder a un debate específico

Todos los recursos privados exigen un JWT válido y el rol adecuado.

🧪 Pruebas sugeridas

✅ Inicio de sesión correcto con credenciales válidas

🚫 Intento de acceso sin token o con token manipulado

🔄 Manejo de expiración del token y renovación

🧾 Validación de permisos al intentar acceder a recursos restringidos

🐞 Pruebas desde Swagger UI simulando distintos roles

📦 Tecnologías principales

Java 17 + Spring Boot 3

Spring Security + JWT

Hibernate / JPA

Flyway para versionado de base de datos

Swagger/OpenAPI para especificaciones técnicas

Maven como gestor de dependencias

🗄️ Base de Datos

Se utiliza MySQL como motor relacional por su rendimiento, amplia compatibilidad y fácil integración con Spring Boot.

Características clave:

✅ Motor: MySQL Server

🗂️ Persistencia gestionada con JPA/Hibernate

🚀 Migraciones controladas con Flyway (src/main/resources/db/migration)

🔐 Integridad y validación mediante esquema SQL

⚙️ Configuración en application.properties

Ejemplo de conexión:

properties

<img width="535" height="119" alt="image" src="https://github.com/user-attachments/assets/fbadf9ea-30e8-4438-86a1-89e9322ad080" />




📸 Evidencias gráficas

Flujo de login con respuesta JWT
<img width="1199" height="357" alt="image" src="https://github.com/user-attachments/assets/e153d385-a155-4268-b9b5-a80fbccc330d" />

 
Ejecución de endpoint protegido con autorización correcta
<img width="920" height="450" alt="image" src="https://github.com/user-attachments/assets/5a8b6f2f-c811-4678-8454-a3abafd73513" />



Respuesta clara ante error 401 y 403 
<img width="917" height="435" alt="image" src="https://github.com/user-attachments/assets/34964726-13fb-4380-be6c-79a8d1d7f6bd" />



📸 Capturas Interfaz Swagger con token insertado y pruebas

Flujo de login y respuesta JWT
<img width="921" height="435" alt="image" src="https://github.com/user-attachments/assets/d5d72805-45a0-4052-b7e2-2ed801b82db7" />

Endpoint protegido accedido con autorización exitosa  
<img width="921" height="736" alt="image" src="https://github.com/user-attachments/assets/d6805d50-c261-4818-953c-a41b5ddc2256" />


Respuesta clara ante error 401 y 403  
<img width="921" height="700" alt="image" src="https://github.com/user-attachments/assets/2325bedf-185d-4005-8fb5-92dc0e1f3ff6" />


🎯 Retos superados

⚙️ Ajuste de dependencias entre Spring Boot 3 y Swagger

🧩 Definición precisa de rutas públicas y privadas

📚 Integración de seguridad en la documentación sin perder usabilidad

🔍 Debug de filtros personalizados para validación de roles

🗂️ Estructura del Proyecto

<img width="329" height="323" alt="image" src="https://github.com/user-attachments/assets/1c3cb501-ddbb-4423-bd2b-48f5c6d2bd9a" />


 

🗂️ Organización del proyecto
controller   → Controladores REST y mapeo de rutas  
domain       → Entidades del modelo de negocio  
dto          → Objetos de transferencia de datos  
respuestas   → Gestión de respuestas y DTOs asociados  
topico       → Entidad que representa los temas del foro  
usuario      → Modelo de usuario del sistema  
infra        → Configuración, seguridad y excepciones  
repository   → Interfaces JPA para acceso a datos  
resources    → Archivos de configuración  
test         → Código de pruebas  
ForoConnectApplication.java → Clase principal

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/346264d9-8c8d-4cd4-9b1e-32ac86dbf46f" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0184b257-f8c9-41c8-b193-f0f34f61d360" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/d5195e16-b4c3-4adc-9318-12465554fa33" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/3cac1132-f925-4daa-acb8-c85b53f291f1" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e30a4ed4-76b2-44d9-a692-43cf1faa8f3c" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e205ab50-5c05-4a83-bdb6-608b8215626b" />








