# Reto 03: layout de aplicación con CSS Grid

## Descripción

Este reto consiste en construir el **layout principal de una aplicación web** utilizando **CSS Grid** como sistema de maquetación bidimensional. También incluye una **galería de imágenes autoajustable** que se adapta al ancho disponible **sin necesidad de media queries**.

Se busca la compresión de cómo organizar una interfaz en áreas visuales (`grid-template-areas`), cómo aplicar distintos tipos de unidades (`fr`, `px`, `auto`), y cómo aprovechar funciones como `repeat()`, `minmax()`, `auto-fit` y `grid-column` para construir un sistema adaptable y moderno.

## Objetivos

- Construir una cuadrícula base utilizando `display: grid`.
- Definir zonas del layout con `grid-template-areas`.
- Establecer dimensiones fijas, flexibles y automáticas (`px`, `fr`, `auto`).
- Aplicar `gap` para separar visualmente los elementos.
- Crear una galería de imágenes que se adapte automáticamente al espacio disponible con `auto-fit` o `auto-fill`.
- Hacer que un elemento se destaque en la galería ocupando varias columnas.

## Acciones realizadas

- Crear la carpeta `reto-03-grid-layout/` con los archivos `index.html` y `style.css`.

### Estructura principal del layout

- Definir una cuadrícula con **3 filas y 3 columnas** que contenga las secciones:
  - `header`
  - `sidebar`
  - `main`
  - `footer`

- Asignar las áreas mediante la propiedad `grid-template-areas`:

  ```css
    grid-template-areas:
      "header header header"
      "sidebar main main"
      "footer footer footer";

- Establecer las dimensiones de las pistas:
    - La sidebar con un ancho fijo:
    ```css
    grid-template-columns: 250px 1fr 1fr;

- El main ocupa el espacio restante con una unidad flexible (1fr).
    - Las filas se definen automáticamente con:
    ```css
    grid-auto-rows: auto;

- Galería de imágenes dentro de main
    - Dentro del main, crear un contenedor con display: grid.

    - Definir una rejilla responsive utilizando:
    ```css
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    ```
    - Añadir espacio entre elementos con gap.
    
    - Incluir un ítem destacado que abarque dos columnas:
    ```css
    grid-column: span 2;
    ```

    

## Referencias útiles

- [MDN Web Docs: CSS Grid Layout](https://developer.mozilla.org/es/docs/Web/CSS/CSS_grid_layout)
- [CSS Tricks: Guía completa de CSS Grid (en inglés)](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [MDN Web Docs: grid-template-areas](https://developer.mozilla.org/es/docs/Web/CSS/grid-template-areas)
- [MDN Web Docs: repeat(), auto-fit, minmax()](https://developer.mozilla.org/es/docs/Web/CSS/repeat)

## Archivos principales

- `index.html`
- `style.css`