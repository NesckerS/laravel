<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

Documentacion de registro con Laravel
# Laboratorio: Autenticación con Laravel Breeze

---

## Introducción

Este laboratorio tiene como objetivo implementar un sistema de autenticación (registro, login y control de acceso) utilizando Laravel. Se trabajó bajo la arquitectura MVC (Modelo-Vista-Controlador):

* Modelos: Representan la estructura de la base de datos (ej. User).
* Vistas: Interfaz de usuario (Blade templates).
* Controladores: Gestionan la lógica de la aplicación.
* Rutas: Definen los endpoints del sistema.

Laravel facilita la integración de estos componentes mediante su estructura organizada y herramientas integradas.

---

## Objetivo del Laboratorio

Implementar un sistema funcional de autenticación utilizando Laravel Breeze, incluyendo:

* Registro de usuarios
* Inicio de sesión
* Protección de rutas
* Manejo de sesiones

---

## Prerrequisitos

### Ecosistema de desarrollo

* PHP 8.3 o superior
* Composer (última versión estable)
* Laravel Installer o Composer
* Servidor local (XAMPP / WampServer / Laragon)
* Servidor web: Apache o Nginx
* Base de datos: MySQL/MariaDB
* Editor: Visual Studio Code
* NPM (Node.js)

### Sistema Operativo

* Windows 10 / 11

---

## Instalación y Configuración

### 1. Crear proyecto

```bash
laravel new mi_app
```

### 2. Entrar al proyecto

```bash
cd mi_app
```

### 3. Instalar dependencias

```bash
composer install
```

### 4. Configurar entorno

```bash
cp .env.example .env
php artisan key:generate
```

Editar `.env`:

```env
DB_DATABASE=mi_app
DB_USERNAME=root
DB_PASSWORD=
```

---

## Instalación de Autenticación (Breeze)

```bash
composer require laravel/breeze --dev
php artisan breeze:install blade
npm install
npm run dev
```

---

## Migraciones

```bash
php artisan migrate
```

En caso de error:

```bash
php artisan migrate:fresh
```

---

## Ejecución del proyecto

```bash
php artisan serve
```

Acceder en:
http://127.0.0.1:8000

---

## Estructura del Proyecto (MVC)

* app/Models → Modelos (ej. User)
* app/Http/Controllers → Controladores
* resources/views → Vistas (Blade)
* routes/web.php → Rutas

---

## Resultado del Sistema

register
<img width="926" height="830" alt="register" src="https://github.com/user-attachments/assets/d131e60f-ef34-408b-b7e1-ae8f38957510" />

login
<img width="860" height="722" alt="login" src="https://github.com/user-attachments/assets/9d851df4-3d41-489a-a2bf-efa0547ee48a" />

---

## Base de Datos

* Motor: MySQL
* Configuración en `.env`
* Migraciones utilizadas:

bash
php artisan migrate


### Backup

Se incluye un respaldo de la base de datos en el repositorio.

---

## Dificultades y Soluciones

Error: PHP version incompatible
Solución: actualizar PHP a 8.3

Error: tabla users ya existe
Solución:

```bash
php artisan migrate:fresh
```

Error: tabla sessions no existe
Solución:

```bash
php artisan session:table
php artisan migrate
```

Error: key too long
Solución:

```php
Schema::defaultStringLength(191);
```

---

## Referencias

https://laravel.com/docs
https://getcomposer.org/
https://www.php.net/

---

## Autor

Este laboratorio ha sido desarrollado por el estudiante de la Universidad Tecnológica de Panamá:

Nombre: Nescker Santana
Correo: nescker.santana@utp.ac.pa
Curso: Desarrollo de Software VII
Instructor del Laboratorio: Irina Fong

---

## Fecha de Ejecución

14 de abril de 2026

