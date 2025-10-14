# Reto 01: Documento jerárquico

## Descripción

Este reto consiste en construir un documento HTML base, completamente aislado, que demuestre el uso correcto del *boilerplate*, las etiquetas semánticas estructurales y una jerarquía de encabezados adecuada. Se prioriza también la accesibilidad, el SEO básico y la optimización de carga de scripts.

## Objetivos

- Usar correctamente la estructura básica de un documento HTML.
- Aplicar la jerarquía de encabezados (`<h1>` a `<h3>`) de forma lógica y accesible.
- Utilizar etiquetas semánticas principales (`<header>`, `<main>`, `<footer>`, `<nav>`, `<aside>`).
- Añadir metadatos esenciales en el `<head>` para compatibilidad, SEO y diseño responsive.
- Simular buenas prácticas de carga de scripts con `async` y `defer`.
- Mantener el documento bien comentado para facilitar su comprensión.

## Acciones realizadas

- Crear la carpeta `reto-01-documento-jerarquico/` y el archivo `index.html`.
- Añadir `lang="es"` al elemento `<html>` para definir el idioma del documento.
- Incluir metadatos en el `<head>`: `charset`, `viewport`, `author` y una `meta description` descriptiva.
- Establecer un `<title>` adecuado y distinto del `<h1>`, para evitar duplicación.
- Añadir un `favicon` para mejorar la experiencia de usuario en el navegador.
- Incorporar estructura semántica básica: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>` y `<footer>`.
- Aplicar una jerarquía de encabezados correcta: un solo `<h1>`, seguido por `<h2>` y `<h3>`.
- Añadir comentarios explicativos en el código para mayor claridad.
- Insertar dos etiquetas `<script>` con los atributos `defer` y `async` al final del `<body>`.

## Sobre la carga de scripts

- **`defer`**: El script se descarga de forma asíncrona y se ejecuta después de que el documento HTML haya sido completamente analizado, garantizando que no bloquee la carga.
- **`async`**: El script se descarga de forma asíncrona y se ejecuta tan pronto como esté disponible, sin esperar a que termine el análisis del documento, útil para scripts independientes.

## Referencias útiles

- [MDN Web Docs: Estructura semántica en HTML](https://developer.mozilla.org/es/docs/Web/HTML/Element)
- [MDN Web Docs: Uso de async y defer](https://developer.mozilla.org/es/docs/Web/HTML/Element/script#attr-async)

## Archivo principal

- `index.html`
