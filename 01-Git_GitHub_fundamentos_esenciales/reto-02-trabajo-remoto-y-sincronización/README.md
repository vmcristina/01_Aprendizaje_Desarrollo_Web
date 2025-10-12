# Reto 02: trabajo remoto y sincronización

Este reto simula un flujo de trabajo real con Git y GitHub: desde la creación del repositorio remoto hasta la sincronización de cambios entre local y remoto.

---
## Objetivos

- Enlazar un repositorio local con GitHub.
- Crear y usar un archivo `.gitignore`.
- Subir cambios al repositorio remoto (`push`).
- Simular cambios remotos y traerlos al local (`pull`).

## Comandos Utilizados

| Comando | Descripción |
|--------|-------------|
| `git remote add origin <URL>` | Enlaza el repositorio local al remoto |
| `git push -u origin main` | Sube el proyecto a GitHub |
| `git pull origin main` | Trae cambios desde GitHub |

## Flujo del reto

1. Se configuró `.gitignore` en la raíz del proyecto.
2. Se preparó y subió el proyecto a GitHub.
3. Se modificó el archivo `README.md` directamente desde GitHub.
4. Se ejecutó `git pull` para traer los cambios al repositorio local.

