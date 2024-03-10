# Proyecto E-commerce Backend con Websockets, MongoDB, Paginación y Sistema de Login

## Descripción
Este proyecto es la continuación del servidor backend para un e-commerce. Incorpora Websockets para actualizaciones en tiempo real, utiliza Handlebars como motor de plantillas, MongoDB con Mongoose para la persistencia de datos, y ahora incluye un sistema de login con roles de usuario y logout.

## Requisitos del Entregable
- Persistencia de productos y carritos en MongoDB.
- Actualizaciones en tiempo real con Websockets.
- Uso de Handlebars para la generación de vistas.
- Implementación de paginación con `mongoose-paginate-v2`.
- Sistema de login con manejo de sesiones.
- Roles de usuario y sistema de logout.

## Objetivos Alcanzados
- CRUD completo para productos y carritos con soporte de MongoDB.
- Actualización en tiempo real de productos y carritos utilizando Websockets.
- Renderizado del lado del servidor con vistas de Handlebars.
- Paginación eficiente de productos y carritos con `mongoose-paginate-v2`.
- Implementación de un sistema de autenticación y autorización de usuarios.

## Instalación y Ejecución
Instala las dependencias del proyecto ejecutando:

```
npm install
```


Inicia el servidor con:

```
npm start
```

## Estructura de Archivos y Directorios

Proyecto/  
│  
├── src/  
│   ├── dao/                 # Acceso a datos para MongoDB y  FileSystem  
│   │   ├── Cart.js  
│   │   ├── CartManager.js  
│   │   ├── Product.js  
│   │   └── ProductManager.js  
│   ├── models/              # Modelos Mongoose  
│   │   ├── Cart.js  
│   │   ├── Product.js  
│   │   └── User.js          # Modelo de usuario  
│   ├── public/              # Archivos estáticos  
│   ├── routes/              # Rutas para productos, carritos y autenticación  
│   │   ├── cartRoutes.js  
│   │   ├── productRoutes.js  
│   │   └── userRoutes.js    # Rutas de autenticación  
│   ├── views/               # Plantillas Handlebars  
│   │   ├── chat.handlebars  
│   │   ├── layouts/  
│   │   ├── home.handlebars  
│   │   ├── realTimeProducts.handlebars  
│   │   └── login.handlebars # Vista de login  
│   ├── controllers/         # Controladores de lógica de negocio  
│   │   └── authController.js  
│   ├── middleware/          # Middlewares de autenticación  
│   │   └── authMiddleware.js  
│   └── app.js               # Configuración de servidor Express y Socket.io  
│  
├── data/                    # Almacenamiento de datos (FileSystem)  
│   ├── carts.json  
│   └── products.json  
│  
├── .gitignore  
├── package.json  
├── package-lock.json  
└── README.md  

## Uso

- Visualización en Tiempo Real: Accede a /realtimeproducts para ver y administrar productos en tiempo real.
- Chat en Vivo: Utiliza el endpoint /chat para interactuar con el chat en tiempo real.
- Autenticación de Usuarios: Regístrate o inicia sesión a través de /login y /logout.
- Gestión de Usuarios: Administra los roles y sesiones de usuarios.

## Pruebas

Además de las pruebas anteriores, asegúrate de realizar pruebas para:

- **Registro e Inicio de Sesión**: Verifica el funcionamiento correcto del registro y el inicio de sesión.
- **Roles de Usuario**: Asegúrate de que los roles de usuario funcionen correctamente, permitiendo acceso administrativo según las credenciales.
- **Logout**: Prueba que el botón de logout cierre la sesión y redirija correctamente.  
  
## Proceso de Testing

### Login por Formulario

- **Inicio en Login:** Al iniciar la aplicación, se deberá mostrar la pantalla de login.
- **Registro de Usuario:** Debe existir un link para registrarse si el usuario es nuevo, redireccionando a un formulario de registro.
- **Validación de Registro:** Verifica que el registro añade al usuario en la base de datos.
- **Prueba de Credenciales Incorrectas:** Intenta iniciar sesión con credenciales incorrectas para confirmar que el acceso es denegado.
- **Prueba de Credenciales Correctas:** Inicia sesión con las credenciales correctas y confirma que se crea la sesión y redirige a la vista de productos.
- **Mensaje de Bienvenida:** Asegúrate de que se muestre un mensaje de bienvenida con los datos del usuario, incluyendo el rol, pero excluyendo la contraseña.
- **Funcionalidad de Logout:** Confirma que el botón de logout destruye la sesión y redirige a la pantalla de login.
- **Acceso de Admin:** Verifica que al ingresar con credenciales de administrador, se redirige correctamente y muestra el rol de 'admin'.
- **Validación de Admin:** Asegura que la cuenta de admin no está almacenada en la base de datos sino que es una validación interna.

Estas pruebas son esenciales para garantizar la funcionalidad correcta del sistema de autenticación y autorización implementado en la Clase 10.

## Contribuciones

Si deseas contribuir a este proyecto, por favor envía un pull request con tus sugerencias o contacta a los administradores del proyecto.

## Licencia
Este proyecto está licenciado bajo la Licencia MIT - ver el archivo LICENSE.md para más detalles.


## Autores y Agradecimientos
[Gona79] - Desarrollo Inicial  
Contribuyentes y revisores que han participado en el proyecto.  
Agradecimientos especiales a todos los que proporcionaron feedback y sugerencias.  
