# Laravel JWT Authentication API

Este proyecto es una API construida con Laravel que implementa autenticación utilizando JSON Web Tokens (JWT) con el paquete `tymon/jwt-auth`.

## Requisitos previos

Asegúrate de tener instalados los siguientes requisitos en tu entorno:

- **PHP 8.0 o superior**
- **Composer**
- **MySQL o cualquier otra base de datos compatible**
- **Servidor web (como Apache o Nginx)**

## Instalación

Sigue los pasos a continuación para configurar el proyecto:

### 1. Clonar el repositorio

```bash
git clone https://github.com/elizabeth011685/jwt-aut-api>
cd jwt-auth-api
```

### 2. Configurar base de datos

Edita el archivo .env ubicado en el directorio raíz del proyecto y configura las credenciales de la base de datos:

```bash
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=jwt_auth
DB_USERNAME=root
DB_PASSWORD=your_password
```
### 3. Ejecutar migraciones

Crea la base de datos configurada y ejecuta las migraciones predeterminadas:

```bash
php artisan migrate
```

### 4. Instalar dependencias

```bash
composer install
```

### 5. Publicar archivo de configuracion de JWT

```bash
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"
```

### 6. Genera la clave secreta para JWT

```bash
php artisan jwt:secret
```

### 7. Iniciar Servidor

```bash
php artisan serve
```

### 8. Probar la API

Utiliza herramientas como Postman o cURL para probar los endpoints:

#### *Registro*

URL: /api/register
Método: POST
Cuerpo:

```bash
{
    "name": "Prueba API Doe",
    "email": "prueba@example.com",
    "password": "password123"
}
```

#### *Inicio de Sesion*

URL: /api/login
Método: POST
Cuerpo:

```bash
{
    "email": "prueba@example.com",
    "password": "password123"
}
```

#### *Obtener usuario autenticado*

URL: /api/me
Método: GET
Encabezado:

```bash
Authorization: Bearer {token}
```

#### *Cerrar sesion*

URL: /api/logout
Método: POST
Encabezado:

```bash
Authorization: Bearer {token}
```
## Notas adicionales

- Protege las rutas sensibles con el middleware auth:api.
- Personaliza los tiempos de expiración del token en el archivo config/jwt.php.
