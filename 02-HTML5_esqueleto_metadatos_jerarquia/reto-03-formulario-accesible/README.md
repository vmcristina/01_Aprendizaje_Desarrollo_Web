# Reto 03: Formulario accesible

## Descripción

Este reto consiste en construir un formulario HTML aislado que demuestre buenas prácticas de accesibilidad, semántica estructural y usabilidad. El objetivo principal es aplicar etiquetas como `<fieldset>`, `<legend>`, y `aria-*`, garantizando que el formulario sea accesible para lectores de pantalla y navegable mediante teclado.

## Objetivos

- Construir la estructura semántica de un formulario usando `<form>`, `<fieldset>` y `<legend>`.
- Asociar correctamente cada campo del formulario con su etiqueta `<label>` mediante el atributo `for`.
- Implementar controles de accesibilidad como `aria-required`, `aria-label` y `tabindex`.
- Implementar navegación con teclado mediante `tabindex`.

## Acciones realizadas

- Crear archivo `formulario.html` en la carpeta `reto-03-formulario-accesible/`.
- Construir el formulario principal con la etiqueta `<form>`.
- Estructurar el formulario con agrupaciones lógicas usando `<fieldset>` y `<legend>`.
- Asociar todos los campos de formulario (`<input>`, `<textarea>`, `<select>`, etc.) con sus respectivas etiquetas `<label>` utilizando `for` + `id`.
- Aplicar `aria-required="true"` a campos obligatorios.
- Configurar orden de navegación con `tabindex`.
- Incluir un botón con icono e `aria-label` para lectores de pantalla.
- Asegurar que el formulario sea semántico, accesible y fácil de usar.

## Referencias útiles

- [MDN Web Docs: Estructura de formularios en HTML](https://developer.mozilla.org/es/docs/Learn/Forms)
- [MDN Web Docs: Atributos ARIA](https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA)
- [MDN Web Docs: Buenas prácticas de accesibilidad en formularios](https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA/forms)

## Archivo principal

- `formulario.html`

