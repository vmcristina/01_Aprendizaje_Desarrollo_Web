# Git & GitHub: fundamentos esenciales

## Descripción general

En esta sección de mi ruta de aprendizaje personal, exploro los fundamentos del control de versiones con **Git** y su integración con **GitHub**.  

## Objetivos de aprendizaje

- Configurar correctamente mi identidad en Git.
- Comprender el área de staging, los commits y el historial local.
- Enlazar y sincronizar un repositorio local con GitHub.
- Usar archivos `.gitignore` para mantener un historial limpio.
- Simular flujos de trabajo profesional con `pull` y `push`.

## Retos realizados

### [Reto 01: Configuración e Historial Local](reto-01-configuracion-historial-local/README.md)

> Primeros pasos con Git en local: configuración de identidad, inicialización de repositorio, área de staging, commits y creación de `README.md`.

**Acciones realizadas:**

- Crear estructura de carpetas y archivo `README.md`
- Inicializar repositorio local con `git init`
- Configurar usuario y email global con `git config`
- Añadir cambios con `git add` y confirmar con `git commit`
- Comprobación del estado con `git status`

### [Reto 02: Trabajo Remoto y Sincronización](reto-02-trabajo-remoto-y-sincronizacion/README.md)

> Conexión de repositorio local con GitHub, uso de `.gitignore`, y práctica de `push` y `pull` para sincronización de cambios.

**Acciones realizadas:**

- Crear nuevo repositorio remoto en GitHub
- Enlazar con repositorio local usando `git remote add origin`
- Crear archivo `.gitignore` básico
- Subir cambios con `git push -u origin main`
- Editar `README.md` desde GitHub y traerlo al local con `git pull`

## Comandos usados

| Comando | Descripción |
|--------|-------------|
| `git config --global user.name "Tu Nombre"` | Configura tu nombre de usuario |
| `git config --global user.email "correo@example.com"` | Configura tu email |
| `git init` | Inicializa un repositorio Git local |
| `git add .` | Añade todos los archivos al staging |
| `git commit -m "mensaje"` | Registra un commit con mensaje |
| `git status` | Muestra el estado del repositorio |
| `git remote add origin <URL>` | Enlaza el repositorio local con uno remoto |
| `git push -u origin main` | Sube los cambios al repositorio remoto |
| `git pull origin main` | Descarga cambios desde GitHub |
| `.gitignore` | Archivo que define qué archivos no subir al repositorio |



