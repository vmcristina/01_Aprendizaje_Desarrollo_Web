# Reto 01: Box Model, posicionamiento y unidades

## Descripción

Este reto consiste en construir una **tarjeta de perfil** que demuestre el uso correcto del modelo de caja en CSS, el posicionamiento de elementos fuera del flujo normal y la aplicación de unidades relativas para lograr un diseño escalable y adaptable.

Se busca practicar conceptos fundamentales como `box-sizing`, el uso de `rem` y `%`, y las propiedades `position` y `z-index` para superponer elementos con precisión.

## Objetivos

- Aplicar el modelo de caja (`box-sizing: border-box`) para controlar correctamente los espacios internos y externos.
- Utilizar unidades relativas (`rem`, `%`) para crear un diseño escalable y responsive.
- Usar propiedades de posicionamiento (`relative`, `absolute`) para colocar elementos fuera del flujo sin alterar la estructura del layout.
- Añadir elementos decorativos superpuestos mediante `z-index`.

## Acciones realizadas

- Crear la carpeta `reto-01-boxmodel-posicionamiento/` y el archivo `index.html` con su respectivo `style.css`.
- Establecer un ancho fijo en `rem` para el contenedor principal de la tarjeta, complementado con un `max-width` en `%` para asegurar una adaptación mínima al ancho del viewport.
- Centrar la tarjeta horizontalmente con `margin: 0 auto` y añadir márgenes y relleno con unidades relativas (`rem`).
- Verificar la aplicación del reset del modelo de caja con `box-sizing: border-box` en todo el documento.
- Definir un elemento decorativo tipo cinta (`badge`) posicionado con `position: absolute` en una de las esquinas, utilizando `top` y `right` negativos para generar una ligera superposición.
- Asegurar que el contenedor tenga `position: relative` para crear un contexto adecuado para los elementos posicionados.
- Incluir un segundo elemento flotante (por ejemplo, un icono de notificación) con `position: absolute` y control de superposición mediante `z-index`.

## Referencias útiles

- [MDN Web Docs: Modelo de caja](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/The_box_model)
- [MDN Web Docs: Propiedades de posicionamiento](https://developer.mozilla.org/es/docs/Web/CSS/position)
- [MDN Web Docs: Unidades en CSS](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Values_and_units)

## Archivos principales

- `index.html`
- `style.css`
