# HTML: Fundamentos de la estructura semántica

## Descripción general

Esta sección forma parte de mi ruta de aprendizaje como desarrolladora web, centrada en dominar la **estructura semántica de HTML** y las buenas prácticas de accesibilidad y organización del contenido.

A lo largo de estos retos, he trabajado con elementos estructurales, contenido multimedia contextualizado, formularios accesibles y navegación por teclado, todo dentro de archivos HTML aislados y comentados para su fácil comprensión.


## Objetivos de aprendizaje

- Crear documentos HTML correctamente estructurados desde cero.
- Utilizar etiquetas semánticas como `<header>`, `<main>`, `<footer>`, `<section>`, `<article>`, entre otras.
- Aplicar la jerarquía de encabezados (`<h1>` a `<h6>`) de forma lógica y accesible.
- Integrar contenido multimedia con contexto mediante `<figure>`, `<figcaption>` e `<iframe>`.
- Construir formularios accesibles utilizando etiquetas `<label>` correctamente asociadas, `aria-*`, `tabindex` y agrupaciones con `<fieldset>`.

## Retos realizados

### [Reto 01: Documento jerárquico](reto-01-documento-jerarquico/README.md)

> Construcción de un documento HTML aislado con una estructura semántica completa, jerarquía de encabezados y carga optimizada de scripts.

### [Reto 02: Contenido con figuras e iframes](reto-02-contenido-figuras/README.md)

> Creación de una galería de contenido multimedia con uso semántico de `<article>`, `<figure>` y contenido embebido mediante `<iframe>`.

### [Reto 03: Formulario accesible](reto-03-formulario-accesible/README.md)

> Desarrollo de un formulario semántico y accesible, usando agrupaciones lógicas, etiquetas correctamente asociadas y atributos ARIA.

## Comandos, etiquetas y atributos utilizados

| Elemento / Atributo HTML | Descripción |
|--------------------------|-------------|
| `<!DOCTYPE html>` | Define el tipo de documento HTML5 (modo estándar). |
| `<html lang="es">` | Idioma del contenido, mejora SEO y accesibilidad. |
| `<head>` | Contenedor de metadatos no visibles en el navegador. |
| `<meta charset="UTF-8">` | Codificación de caracteres para acentos y símbolos. |
| `<meta name="viewport">` | Diseño responsive en dispositivos móviles. |
| `<meta name="author">` | Información del autor del documento. |
| `<meta name="description">` | Breve descripción del contenido para SEO. |
| `<title>` | Título visible en la pestaña del navegador. |
| `<link rel="icon">` | Define un favicon para la página. |
| `<header>`, `<main>`, `<footer>` | Estructura semántica principal de la página. |
| `<nav>` | Área de navegación con enlaces. |
| `<aside>` | Contenido complementario o adicional. |
| `<section>` | Agrupación semántica de contenido temático. |
| `<article>` | Contenido independiente y reutilizable (entradas, tarjetas, etc.). |
| `<h1>` a `<h3>` | Encabezados jerárquicos correctamente anidados. |
| `<p>` | Párrafo de texto. |
| `<ul>`, `<li>` | Lista desordenada para navegación u organización de ítems. |
| `<a href="">` | Enlaces internos o externos (con `target="_blank"` y `rel="noopener noreferrer"` para seguridad). |
| `<figure>`, `<figcaption>` | Agrupación de imagen + descripción contextual. |
| `<img src="" alt="">` | Imagen con texto alternativo para accesibilidad. |
| `style="max-width: XX%; height: auto;"` | Estilos inline para controlar el tamaño de imágenes. |
| `<iframe>` | Inserción de contenido externo (Google Maps). |
| `loading="lazy"` | Carga diferida del contenido embebido para mejorar rendimiento. |
| `referrerpolicy="no-referrer-when-downgrade"` | Controla qué datos se envían al abrir iframes externos. |
| `<form action="#" method="post">` | Formulario semántico con método POST. |
| `<fieldset>`, `<legend>` | Agrupación lógica de campos de formulario. |
| `<label for="id">` | Asociación explícita entre campo y etiqueta. |
| `<input type="text/email/tel/checkbox">` | Diferentes tipos de campos de entrada. |
| `<textarea rows="" cols="">` | Campo para texto largo. |
| `<select>`, `<option>` | Menú desplegable con opciones de selección. |
| `<button type="submit">` | Botón de envío del formulario. |
| `aria-required="true"` | Marca un campo como obligatorio para lectores de pantalla. |
| `aria-label="..."` | Descripción alternativa accesible para iconos o botones. |
| `tabindex="1"` a `tabindex="8"` | Orden de navegación con teclado. |
| `<script defer>` / `<script async>` | Carga no bloqueante de scripts externos. |

## Referencias útiles

- [MDN Web Docs: Estructura semántica en HTML](https://developer.mozilla.org/es/docs/Web/HTML/Element)
- [MDN Web Docs: Uso de async y defer](https://developer.mozilla.org/es/docs/Web/HTML/Element/script#attr-async)
- [MDN Web Docs: Uso de `<figure>` y `<figcaption>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/figure)
- [MDN Web Docs: Uso de `<iframe>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/iframe)
- [MDN Web Docs: Estructura de formularios en HTML](https://developer.mozilla.org/es/docs/Learn/Forms)
- [MDN Web Docs: Atributos ARIA](https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA)
- [MDN Web Docs: Buenas prácticas de accesibilidad en formularios](https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA/forms)

