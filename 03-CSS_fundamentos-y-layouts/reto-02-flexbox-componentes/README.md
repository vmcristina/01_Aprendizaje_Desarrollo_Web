# Reto 02: navegación y componentes con Flexbox

## Descripción

En este reto se propone construir dos componentes fundamentales de una interfaz moderna: una **barra de navegación adaptable** y un **listado flexible de tarjetas de producto**. Ambos deben estructurarse utilizando **Flexbox** para asegurar alineación precisa, distribución del espacio y adaptabilidad sin necesidad de media queries.

El ejercicio está enfocado en comprender la maquetación unidimensional y aplicar propiedades clave como `justify-content`, `align-items`, `flex-wrap` y `flex`.

## Objetivos

- Utilizar `display: flex` para construir estructuras horizontales y verticales flexibles.
- Distribuir elementos dentro de un contenedor mediante `justify-content` y `align-items`.
- Implementar la propiedad `gap` para espaciar elementos sin depender de márgenes.
- Permitir que un conjunto de tarjetas se ajuste automáticamente al ancho disponible con `flex-wrap`.
- Controlar el tamaño y comportamiento de las tarjetas con `flex: grow shrink basis`.

## Acciones realizadas

- Crear la carpeta `reto-02-flexbox-componentes/` con su archivo `index.html` y su hoja de estilos correspondiente.

### Barra de navegación
- Construir un `<nav>` que agrupa tres zonas: logo, navegación principal y accesos de usuario.
- Aplicar `display: flex` y `justify-content: space-between` para alinear los grupos en los extremos.
- Usar `align-items: center` para alinear verticalmente el contenido.
- Incluir `gap` entre elementos del menú para mejorar la separación interna sin usar márgenes individuales.

### Listado de tarjetas
- Crear un contenedor para tarjetas de producto con `display: flex` y `flex-wrap: wrap`, permitiendo que los elementos salten de línea si no hay espacio.
- Configurar cada tarjeta con `flex: 1 1 300px` para que tenga una base mínima y se adapte al espacio disponible.

## Referencias útiles

- [MDN Web Docs: Flexbox](https://developer.mozilla.org/es/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [CSS Tricks: Guía completa de Flexbox (en inglés)](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [MDN Web Docs: Propiedad `order`](https://developer.mozilla.org/es/docs/Web/CSS/order)

## Archivos principales

- `index.html`
- `style.css`
