# Proyecto Laravel con Sail / Filament v4
Este es un proyecto Laravel configurado para usar Laravel Sail como entorno de desarrollo local con Docker y un panel administrativo en Filament V4.

## Requisitos Previos
Docker

## Instalación
**1. Clonar el proyecto**
```bash
    git clone git@github.com:allencarlosdev/Test-FilamentV4.git
```
**2. Entrar al proyecto**
```bash
    cd Test-FilamentV4
```
**3. Configurar variables de entorno**
   En la consola agregas lo siguiente:
```bash
    cp .env.example .env
```
**4. Configuras las variables de entorno**
```bash
    DB_CONNECTION=
    DB_HOST=
    DB_PORT=
    DB_DATABASE=
    DB_USERNAME=
    DB_PASSWORD=
```

**5. Instalas la Imagen de sail 8.4 e instala las dependencias en el contenedor**
    Esto lo colocas en tu consola :
```bash
    docker run --rm \
        -u "$(id -u):$(id -g)" \
        -v "$(pwd):/var/www/html" \
        -w /var/www/html \
        laravelsail/php84-composer:latest \
        composer install --ignore-platform-reqs
```

**6. Levantas los contenedores del Proyecto en Docker**
    Esto lo colocas en tu consola :
```bash
     ./vendor/bin/sail up -d
```

**6.1 Cambiar el alias ( Opcional )**
    Esto lo colocas en tu consola :
```bash
    echo 'alias sail="./vendor/bin/sail"' >> ~/.bashrc
    source ~/.bashrc
```

**7 Generar una nueva Key**
    Esto lo colocas en tu consola :
```bash
    sail artisan key:generate
```
**8 Migrar las tablas de la base de datos**
    Esto lo colocas en tu consola :
```bash
    sail artisan migrate
```
**9 El proyecto de laravel ya esta en marcha**
    Esto lo colocas en tu browser :
    (http://localhost:8083)

**10 Para ingresar a Filament debes ir :**
    Esto lo colocas en tu browser :
    (http://localhost:8083/admin)

**11 Ingresa el usuario o crear uno :**
    Esto lo colocas en tu consola :
```bash
    sail artisan make:filament-user
```
Si ya existe algun usuario en el seed puedes ejecutar:

```bash
    sail artisan db:seed
```
