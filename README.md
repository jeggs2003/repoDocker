# Parcial 1179222 - Docker

Este proyecto consiste en el despliegue de una arquitectura de tres capas (Web, App y DB) utilizando **Docker** y **Docker Compose** en un entorno de **Ubuntu Server**.

## 🏗️ Estructura de la Solución

La infraestructura se divide en tres servicios interconectados:

* **Servicio Web (Nginx):** Actúa como un proxy inverso que recibe las peticiones y las redirige al servidor de aplicaciones.
* **Servicio App (Apache/PHP):** Contiene la lógica de negocio y procesa las peticiones dinámicas.
* **Servicio DB (MySQL):** Gestiona la persistencia de datos y se inicializa automáticamente con scripts SQL.

## 📁 Estructura del Repositorio

```text
.
├── app/
│   ├── src/index.php          # Código fuente de la aplicación
│   ├── apache-vhost.conf      # Configuración de Virtual Host
│   └── Dockerfile             # Definición de imagen Apache/PHP
├── db/
│   └── init/01-init.sql       # Script de creación de tablas/datos
├── web/
│   ├── certs/                 # Certificados de seguridad
│   ├── nginx.conf             # Configuración del Proxy Inverso
│   └── Dockerfile             # Definición de imagen Nginx
├── .env                       # Variables de entorno
└── docker-compose.yml         # Orquestación de contenedores
