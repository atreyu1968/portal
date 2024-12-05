# Portal de Educación

Sistema de gestión de contenidos (CMS) moderno y flexible desarrollado con React, TypeScript y Tailwind CSS.

## Características

### 🎨 Editor Visual
- Editor de páginas con componentes drag & drop
- Carrusel de imágenes con autoplay
- Secciones de texto enriquecido
- Galerías multimedia
- Formularios personalizables
- Acordeones
- Videos embebidos
- HTML/CSS personalizado
- Scripts JavaScript
- Markdown

### 🛠 Panel de Administración
- Gestión de páginas
- Editor de carrusel
- Gestión de redes
- Gestión de servicios
- Biblioteca de medios
- Gestión de formularios
- Editor de navegación
- Gestión de administradores
- Configuración del sitio

### 🎯 Características Principales
- Diseño responsive
- Efecto glassmorphism en cabecera
- Optimización SEO
- Caché de assets
- Compresión Gzip
- Seguridad mejorada
- Soporte para favicon
- Integración con redes sociales

## Requisitos

- Node.js 20.x o superior
- NPM 10.x o superior
- Nginx
- Docker y Docker Compose (opcional)

## Instalación Local

1. Clonar el repositorio:
```bash
git clone <repositorio>
cd portal-educacion
```

2. Instalar dependencias:
```bash
npm install
```

3. Iniciar en modo desarrollo:
```bash
npm run dev
```

## Despliegue en Debian

### Método 1: Instalación Manual

1. Actualizar el sistema:
```bash
sudo apt update && sudo apt upgrade -y
```

2. Instalar Node.js y npm:
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
```

3. Instalar Nginx:
```bash
sudo apt install nginx -y
```

4. Clonar y construir el proyecto:
```bash
git clone <repositorio>
cd portal-educacion
npm install
npm run build
```

5. Configurar Nginx:
```bash
sudo nano /etc/nginx/sites-available/portal-educacion
```

Copiar la configuración del archivo `nginx.conf` proporcionado.

6. Habilitar el sitio:
```bash
sudo ln -s /etc/nginx/sites-available/portal-educacion /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl restart nginx
```

### Método 2: Usando Docker (Recomendado)

1. Instalar Docker y Docker Compose:
```bash
# Docker
curl -fsSL https://get.docker.com | sudo sh
sudo usermod -aG docker $USER

# Docker Compose
sudo apt install docker-compose-plugin
```

2. Clonar el repositorio:
```bash
git clone <repositorio>
cd portal-educacion
```

3. Construir y ejecutar:
```bash
docker compose up -d
```

## Estructura del Proyecto

```
├── src/
│   ├── components/     # Componentes React
│   ├── lib/           # Utilidades y configuración
│   ├── pages/         # Páginas de la aplicación
│   └── types/         # Definiciones TypeScript
├── public/            # Archivos estáticos
└── docker/           # Configuración Docker
```

## Seguridad

El proyecto incluye varias medidas de seguridad:

- Headers de seguridad HTTP
- Sanitización de HTML
- Protección XSS
- Políticas CSP
- Sandboxing para scripts y HTML personalizados

## Mantenimiento

### Backups

Configurar respaldo periódico de:
- Archivos de la biblioteca de medios
- Base de datos local
- Configuración del sitio

### Monitorización

```bash
# Ver logs de Docker
docker compose logs -f

# Monitorizar recursos
docker stats
```

### Actualización

1. Detener servicios:
```bash
docker compose down
```

2. Actualizar código:
```bash
git pull
```

3. Reconstruir y reiniciar:
```bash
docker compose up -d --build
```

## Licencia

Este proyecto está bajo la licencia MIT. Ver el archivo `LICENSE` para más detalles.