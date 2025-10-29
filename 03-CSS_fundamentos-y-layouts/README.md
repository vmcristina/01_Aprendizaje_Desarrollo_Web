# Fundamentos y maquetación en CSS

Este documento recopila los **principales conceptos de CSS** organizados por módulos de aprendizaje.  
Incluye teoría, objetivos y ejemplos prácticos sobre **Box Model, Posicionamiento, Flexbox, Grid y diseño responsive**.

## Módulos de aprendizaje

1. [Fundamentos y flujo (Box Model + position)](#modulo-1)  
2. [Flexbox: maquetación 1D](#modulo-2)  
3. [Grid: maquetación 2D](#modulo-3)  
4. [Responsive y variables CSS](#modulo-4)  
5. [Arquitectura y preprocesadores (SASS/SCSS)](#modulo-5)

---

<a id="modulo-1"></a>
## 🔸 Módulo 1: fundamentos y flujo de CSS

### Objetivos

- Comprender cómo CSS aplica los estilos (cascada y especificidad).  
- Dominar el **modelo de caja (Box Model)**.  
- Entender el **flujo normal del documento** y cómo modificarlo con `position`.  

### Conceptos clave

| Concepto | Explicación rápida | Ejemplo |
|-----------|--------------------|----------|
| **Cascada** | El navegador decide qué regla aplicar según origen, especificidad y orden. | `!important` tiene máxima prioridad. |
| **Especificidad** | Los selectores más precisos ganan. | `#id` > `.clase` > `elemento`. |
| **Flujo normal** | Bloques se apilan verticalmente, inlines fluyen en línea. | `<div>` vs `<span>`. |
| **display** | Define el comportamiento visual. | `inline-block`, `flex`, `grid`, etc. |
| **Herencia** | Algunas propiedades se heredan automáticamente. | `body { color: blue; }` → `p` azules. |

### Modelo de caja (Box model)

Cada elemento es una caja con: **contenido → padding → border → margin**  
Usar `box-sizing: border-box;` para simplificar cálculos.

```css
/* Reset profesional */
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

**Propiedades principales**

- `width`, `height`: tamaño del contenido.  
- `padding`, `margin`: espacios internos/externos.  
- `border`: borde visible.  
- `overflow`: control del contenido que se sale.  
- `background`, `opacity`, `cursor`: aspecto e interacción.

### Posicionamiento (`position`)

| Valor | Descripción | Comportamiento |
|--------|--------------|----------------|
| `static` | Por defecto, sigue el flujo normal. | No acepta `top`, `left`, etc. |
| `relative` | Se mueve respecto a su posición original. | Deja su hueco. |
| `absolute` | Se retira del flujo. | Se posiciona relativo al ancestro posicionado. |
| `fixed` | Fijo respecto al viewport. | No se mueve con el scroll. |
| `sticky` | Mezcla entre relative y fixed. | Se fija al alcanzar un umbral. |

**Tip:** `z-index` controla la superposición (solo si `position ≠ static`).

### Unidades útiles

| Tipo | Unidad | Ejemplo | Uso |
|------|---------|----------|------|
| Absoluta | `px` | `width: 200px;` | Bordes, detalles. |
| Relativa al padre | `%` | `width: 50%;` | Layouts fluidos. |
| Relativa al root | `rem` | `font-size: 1.2rem;` | Tipografía y spacing global. |
| Viewport | `vh`, `vw` | `height: 100vh;` | Secciones de pantalla completa. |

### Buenas prácticas

- Coloca tus hojas CSS al final del `<head>` para evitar parpadeos.  
- Usa `!important` solo en casos justificados.  
- Aplica `rem` para mantener escalabilidad.  

### [Reto 01: Box Model, posicionamiento y unidades](reto-01-boxmodel-posicionamiento/README.md)

> Construir una tarjeta de perfil que practique el modelo de caja, posicionamiento y unidades relativas en CSS para un diseño escalable y adaptable.

---

<a id="modulo-2"></a>
## 🔸 Módulo 2: Flexbox (maquetación 1D)

### Objetivos

- Comprender cómo funciona el **modelo flexible**.  
- Dominar alineaciones, distribuciones y tamaños en un solo eje.  

### Propiedades del contenedor (Padre)

| Propiedad | Valores principales | Función |
|------------|---------------------|----------|
| `display` | `flex` | Activa el modo flexible. |
| `flex-direction` | `row` / `column` | Eje principal. |
| `justify-content` | `center`, `space-between` | Distribuye en el eje principal. |
| `align-items` | `center`, `stretch` | Alinea en el eje cruzado. |
| `align-content` | Es como align-items, pero para varias líneas |
| `flex-wrap` | `wrap` | Permite que los ítems pasen a otra línea. |
| `gap` | `1rem`, `10px`, etc. | Espacio entre ítems. |

```css
/* Ejemplo de contenedor Flexbox */
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  align-content: stretch;
  gap: 1rem;
}
```

### Propiedades de los ítems (Hijos)

| Propiedad | Función | Ejemplo |
|------------|----------|----------|
| `order` | Cambia el orden visual. | `order: 2;` |
| `flex-grow` | Capacidad de crecer. | `flex-grow: 1;` |
| `flex-shrink` | Capacidad de encogerse. | `flex-shrink: 0;` |
| `flex-basis` | Tamaño base inicial. | `flex-basis: 200px;` |
| `flex` | Atajo `flex-grow flex-shrink flex-basis`    |
| `align-self` | Alineación individual. | `align-self: center;` |

```css
/* Ejemplo de ítems Flexbox */
.item {
  flex: 1 1 150px; /* grow, shrink, base */
  order: 0;
  align-self: auto;
}
```

### Patrones comunes

**Centrar un elemento (horizontal y verticalmente)** 

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

**Distribución de Navbar**  

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

**Separadores sin márgenes** 

```css
.container {
  display: flex;
  gap: 0; /* elimina espacio entre ítems */
}
```

### [Reto 02: navegación y componentes con Flexbox](reto-02-flexbox-componentes/README.md)

> Construir una barra de navegación adaptable y un listado de tarjetas de producto usando Flexbox para lograr alineación y distribución flexibles sin media queries.

---

<a id="modulo-3"></a>
## 🔸 Módulo 3: CSS Grid (Maquetación 2D)

## Objetivos del módulo

Dominar **CSS Grid** como herramienta de maquetación bidimensional.  
Aprender a definir filas y columnas explícitas, usar áreas nombradas y combinar Grid con Flexbox para crear layouts completos y responsivos.

## Grid: el contenedor (padre)

Para activar Grid, el contenedor debe tener `display: grid`.  
Desde ahí se definen las filas, columnas, áreas y la alineación general.

| Propiedad | Ejemplo / Valor | Descripción |
|------------|------------------|-------------|
| `display` | `grid` | Activa el contexto de cuadrícula. |
| `grid-template-columns` | `1fr 2fr 1fr`, `repeat(3, 1fr)` | Define las columnas. |
| `grid-template-rows` | `auto 1fr auto` | Define las filas. |
| `grid-template-areas` | `"header header" "sidebar main"` | Nombra las áreas de la cuadrícula. |
| `gap` | `1rem`, `20px 10px` | Espacio entre filas y columnas. |
| `grid-auto-flow` | `row`, `column`, `dense` | Controla el flujo automático de los ítems. |
| `justify-items` / `align-items` | `center`, `stretch`, etc. | Alineación interna de los ítems. |
| `justify-content` / `align-content` | `center`, `space-between`, etc. | Alineación de la cuadrícula completa. |

## Unidades y funciones esenciales en Grid

| Unidad / Función / Valor | Tipo | Descripción |
|------------------|------|--------------|
| `fr` | unidad | Divide el espacio sobrante proporcionalmente. |
| `repeat()` | función | Repite valores sin escribirlos manualmente. |
| `minmax()` | función | Define un rango mínimo y máximo para una pista. |
| `auto` | valor | Ajusta la pista al contenido del ítem. |
| `auto-fit` / `auto-fill` | valor + función | Crean cuadrículas dinámicas y responsivas que ajustan el número de columnas según el ancho disponible. `auto-fill` crea columnas vacías; `auto-fit` las colapsa, permitiendo que las columnas visibles se estiren. |

## Grid: los ítems (hijos)

Estas propiedades controlan cómo se colocan los elementos dentro del grid:

| Propiedad | Ejemplo / Valor | Descripción |
|------------|------------------|-------------|
| `grid-area` | `header`, `main`, etc. | Asigna el ítem a un área nombrada. |
| `grid-column` | `1 / 4`, `span 2` | Líneas de inicio y fin de columnas. |
| `grid-row` | `2 / 3`, `span 1` | Líneas de inicio y fin de filas. |
| `justify-self` / `align-self` | `center`, `stretch`, etc. | Alineación individual del ítem dentro de su celda. |
| `order` | número entero | Cambia el orden visual del ítem. |

## Patrones profesionales con Grid

- **Layout completo (macro):** define cabecera, sidebar, contenido y pie de página.  
- **Componentes internos con Flexbox:** usa Flexbox dentro de las celdas para alinear ítems (listas, menús, botones…).  
- **Grid + Flexbox:** Grid para estructura 2D global, Flexbox para organización interna 1D.  
- **Layouts responsivos:** `auto-fit` y `auto-fill` permiten cuadrículas que se adaptan sin media queries.  
- **Áreas dinámicas:** cambia la disposición del layout modificando `grid-template-areas` en media queries para reorganizar la disposición del layout sin mover el HTML.

## Ejemplo práctico de layout con Grid

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-template-columns: 200px 1fr;
  grid-template-rows: auto 1fr auto;
  gap: 1rem;
}

.header {
  grid-area: header;
}

.sidebar {
  grid-area: sidebar;
}

.main {
  grid-area: main;
}

.footer {
  grid-area: footer;
}
```

### Explicación

- Se crea un layout con **3 filas y 2 columnas**.  
- Cada área (header, sidebar, main, footer) se define por nombre.  
- El `gap` separa visualmente las celdas.  
- Cada ítem se ubica mediante su propiedad `grid-area`.

## Buenas prácticas

- Usa **media queries** para modificar áreas o columnas según el ancho.  
- Aprovecha `minmax()` y `auto-fit` para mantener flexibilidad.  
- Usa `subgrid` (cuando esté disponible) para heredar líneas de cuadrícula.  
- Evita el uso innecesario de `!important`.  
- Usa las **DevTools** del navegador para visualizar líneas y áreas.  
- Define **fallbacks** con Flexbox o `block` para navegadores antiguos.

### [Reto 03: layout de aplicación con CSS Grid](reto-03-grid-layout/README.md)

> Construir el layout principal de una web y una galería de imágenes autoajustable usando CSS Grid, adaptable sin media queries.

---

<a id="modulo-4"></a>
## 🔸 Módulo 4: diseño responsive y variables CSS

## Objetivos del módulo

Aprender a diseñar con enfoque **Mobile First**, adaptando el contenido a distintos tamaños de pantalla,  
y dominar las **variables CSS nativas (`--var`)** para mantener consistencia y escalabilidad visual.

## Diseño responsive y media queries

El enfoque **Mobile First** comienza con estilos base para móviles y agrega mejoras progresivas con `@media (min-width)` para pantallas más grandes.

| Concepto | Descripción | Ejemplo |
|-----------|--------------|---------|
| **Viewport meta tag** | Define el área visible y el escalado en dispositivos móviles. | `<meta name="viewport" ...>` |
| **Mobile First** | Los estilos base se aplican sin media queries. | `body { font-size: 16px; }` |
| **Media Queries** | Condiciones para adaptar el diseño. | `@media (min-width: 768px)` |
| **min-width** | Base del enfoque Mobile First. | Aplica estilos hacia arriba. |
| **max-width** | Enfoque Desktop First. | Aplica estilos hacia abajo. |
| **object-fit** | Controla cómo se adaptan imágenes o vídeos. | `object-fit: cover;` |
| **Unidades relativas** | Mejor adaptabilidad que px. | `rem`, `%`, `vw`, `vh`. |

## Variables CSS nativas (Custom Properties)

Las *variables CSS* permiten mantener consistencia visual, reutilizar valores y crear temas dinámicos (dark mode, branding, etc.).

| Concepto | Descripción | Ejemplo |
|-----------|--------------|---------|
| **Definición** | Se crean con `--nombre-variable`. | `--color-primario: #007bff;` |
| **Ámbito global (`:root`)** | Variables accesibles en todo el proyecto. | `:root { --spacing-base: 1rem; }` |
| **Uso con `var()`** | Accede al valor de la variable. | `color: var(--color-primario);` |
| **Fallback** | Valor de respaldo si no existe la variable. | `color: var(--texto, black);` |
| **Ámbito local** | Variables definidas dentro de un selector específico. | `.card { --sombra: 2px; }` |
| **Theming dinámico** | Cambiar variables para temas (ej. modo oscuro). | `.dark-theme { --color-bg: #000; }` |

### Puntos de ruptura personalizados

Crea breakpoints según el contenido, no por dispositivos específicos.  

```css
@media (min-width: 480px) { /* Móviles grandes */ }

@media (min-width: 768px) { /* Tablets */ }

@media (min-width: 1024px) { /* Escritorio */ }
```

### Escalado de tipografía

Usa `rem` en lugar de `px` como unidad base y ajusta el tamaño del `<html>` en media queries para escalar toda la interfaz de usuario (UI).  

```css
/* Estilos base (móvil) */
html {
  font-size: 16px; 
}

/* Estilos para pantallas grandes (tablet y superior) */
@media (min-width: 768px) {
  html {
    font-size: 17.6px; /* escala un 10% */
  }
}
```

### Organización de variables

Agrupa las variables por categorías dentro de `:root` para mantener orden y escalabilidad.  

```css
:root {
  /* Colores */
  --color-primario: #ff006aff;
  --color-secundario: #f8f8f8;

  /* Tipografía */
  --font-base: 1rem;
  --font-titulo: 1.5rem;

  /* Espaciado */
  --spacing-xs: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 2rem;
}
```

### Modo oscuro con CSS puro

Redefine variables dentro de una clase `.dark-theme` para cambiar los valores dinámicamente, sin hacer uso de JavaScript.  

```css
:root {
  --color-bg: white;
  --color-texto: black;
}

.dark-theme {
  --color-bg: #111;
  --color-texto: #eee;
}

body {
  background-color: var(--color-bg);
  color: var(--color-texto);
}
```

## Buenas prácticas

- Agrupa variables por categorías y usa comentarios claros.  
- Usa **nombres semánticos** (`--color-boton`, no `--azul1`).  
- Evita duplicados: reutiliza variables existentes.  
- Usa unidades relativas (`rem`, `%`) para escalabilidad.  
- Define un sistema de diseño (Design Tokens) desde el inicio.   
- Empieza siempre **mobile-first** y escala hacia pantallas grandes.  
- Integra tus variables con tus herramientas de desarrollo.

### [Reto 04: diseño responsive y theming con variables CSS](reto-04-responsive-theming/README.md)

> Hacer el layout del Reto 03 completamente responsive (Mobile First) y configurable con variables CSS, incluyendo modo oscuro automático y adaptación a distintos tamaños de pantalla.

---

<a id="modulo-5"></a>
## 🔸 Módulo 5: arquitectura y preprocesadores (SASS / SCSS)

## Objetivos del módulo

Dominar **SASS/SCSS** para crear código modular, escalable y mantenible, aplicando principios de arquitectura CSS (BEM, ITCSS) en proyectos grandes y colaborativos.

## ¿Qué es un preprocesador?

Los preprocesadores amplían las capacidades de CSS con lógica, reutilización y modularidad (variables estáticas, mixins, funciones, anidamiento…).  
El navegador **no interpreta SASS directamente**, por lo que debe **compilarse a CSS** antes de usarse.

**Diferencias de sintaxis:**
- **SCSS:** sintaxis moderna (con llaves y punto y coma).  
- **SASS:** sintaxis antigua (basada en indentación).  

## Funcionalidades esenciales

| Concepto | Ejemplo / Sintaxis | Descripción |
|-----------|--------------------|-------------|
| **Variables** | `$color-primario: #ff1e1eff;` | Valores reutilizables, estáticos y centralizados. |
| **Mapas** | `map-get($colores, primario)` | Estructuras clave–valor para organizar datos. |
| **Anidamiento** | `nav { ul { li { a { ... }}}}` | Replica la jerarquía del HTML; evita repetición de selectores. |
| **Mixins** | `@mixin`, `@include` | Bloques reutilizables con parámetros opcionales. |
| **@content** | `@mixin nombre { @content; }` | Inyecta código dentro de un mixin (gran flexibilidad). |
| **Funciones** | `@function nombre() { ... }` | Devuelven valores calculados dinámicamente. |
| **Operadores** | `+ - * / %` | Permiten cálculos numéricos o de color. |
| **Partials** | `_nombre.scss` | Archivos modulares que se importan en otros. |
| **Importación / uso** | `@import` / `@use` | Permite componer estilos desde varios archivos. |

## Variables y mapas SASS

Las variables SASS permiten centralizar colores, tamaños o espaciados para que un cambio global afecte a todo el proyecto.  
Los mapas SASS almacenan pares **clave → valor**, útiles para paletas o breakpoints.

```scss
// Variables simples
$color-primario: #00ff4cff;
$spacing-base: 1rem;

// Mapa de colores
$colores: (
  primario: #00ff4cff,
  secundario: #f8f8f8,
  texto: #080808ff
);

// Acceso al mapa
.button {
  background-color: map-get($colores, primario);
}
```

## Anidamiento (Nesting)

Escribir selectores jerárquicos que reflejan la estructura del HTML mejora la legibilidad y reduce repeticiones.

```scss
.nav {
  background: $color-primario;
  ul {
    list-style: none;
    li {
      display: inline-block;
      a {
        color: white;
      }
    }
  }
}
```

## Funciones personalizadas

Permiten cálculos o transformaciones reutilizables dentro del CSS, como ajustar colores o dimensiones.

```scss
@function doble($valor) {
  @return $valor * 2;
}

.ancho {
  width: doble(10px); // 20px
}
```

## Mixins (modularidad y lógica)

Los **mixins** son bloques de código reutilizables con parámetros y valores por defecto. Se combinan con `@include` para aplicar la lógica donde sea necesario.

```scss
@mixin boton($color: #6e0000ff, $padding: 1rem) {
  background-color: $color;
  padding: $padding;
  border: none;
  color: white;
  border-radius: 4px;
}

.btn {
  @include boton(); // Usa valores por defecto
}

.btn-secundario {
  @include boton(#333, 0.5rem); // Personaliza valores
}
```

### Regla `@content` (inyección de bloque)

`@content` permite crear mixins flexibles que reciben bloques de CSS personalizados (ideal para media queries).

```scss
@mixin responsive($breakpoint) {
  @media (min-width: $breakpoint) {
    @content; // Inserta el bloque CSS que se pasa al incluir el mixin
  }
}

.container {
  padding: 1rem;

  @include responsive(768px) {
    display: flex;
    gap: 2rem;
  }
}
```
Otro ejemplo válido usa una media query para móvil, donde el código del selector se inyecta dentro de la consulta.

```scss
@mixin movil {
  @media screen and (max-width: 480px) {
    @content; // Aquí se inyecta el código del selector
  }
}

p {
  font-size: 4em;

  @include movil { // El código entre llaves se inyecta en @media
    font-size: 2em;
  }
}
```

> 📌 **Tip pro:** Combina argumentos y `@content` para lograr un control similar a una función aplicada a estructuras completas.

## Diferencias: SASS vs CSS nativo

| Característica | Variables SASS ($) | Variables CSS (--var) |
|----------------|--------------------|-----------------------|
| **Compilación** | Tiempo de build | Tiempo de ejecución |
| **Ámbito** | Archivos / módulos | DOM (`:root`, clases) |
| **Dinamismo** | Estático | Dinámico (JS / theming) |
| **Extras** | Mixins, funciones, operadores | Solo `var()` y `calc()` |
| **Uso ideal** | Lógica y valores fijos | Theming y cambios dinámicos |

## Herramientas de compilación

Para convertir SASS/SCSS a CSS, se necesita un compilador. La elección depende del stack del proyecto.

| Herramienta | Descripción | Contexto |
|--------------|-------------|-----------|
| **Dart Sass** | Implementación oficial y actualizada. | CLI o scripts de build. |
| **Node-sass** | Más antiguo y rápido, ya en desuso. | Proyectos legacy. |
| **Webpack / Vite (sass-loader)** | Integra SASS en pipelines JS. | React, Vue, Angular. |
| **Gulp / Grunt** | Automatizadores de tareas. | Proyectos personalizados. |
| **Prepros / Koala** | GUI para compilación en vivo. | Ideal para aprendizaje. |
| **Herramientas online** | Compiladores web rápidos. | Tests o ejemplos. |

## Arquitectura y escalabilidad CSS

Una buena arquitectura permite mantener estilos claros, modulares y predecibles.

| Concepto | Descripción | Propósito |
|-----------|--------------|------------|
| **BEM** | `.bloque__elemento--modificador` | Claridad y bajo acoplamiento. |
| **ITCSS** | Capas de estilos de genérico → específico | Controlar cascada y especificidad. |
| **Atomic CSS** | Clases pequeñas y reutilizables | Rapidez y consistencia (base de Tailwind). |
| **Escalas de espaciado** | Variables con incrementos regulares | Coherencia visual global. |

## Buenas prácticas

- Usa **partials** (`_archivo.scss`) para variables, mixins, componentes y layouts.  
- Evita **anidar más de 3 niveles** de selectores.  
- Combina **SASS para lógica** y **CSS variables para theming dinámico**.  
- Activa **sourcemaps** para depuración fácil.  
- Usa nombres **semánticos** y consistentes.  

## BEM ( Block / Element / Modifier )

Convención de nombres que evita conflictos de especificidad.  
Ejemplo práctico:

```html
<button class="btn btn--primario btn--grande">Enviar</button>
```
```scss
.btn {
  padding: 1rem;
  &--primario {
    background-color: blue;
  }
  &--grande {
    font-size: 1.2rem;
  }
}
```

## ITCSS (Inverted Triangle CSS)

Organiza el proyecto en capas jerárquicas:
1. Configuración (variables, mixins).  
2. Herramientas.  
3. Estilos base.  
4. Objetos y componentes.  
5. Utilidades.  

Esta estructura minimiza conflictos y facilita la escalabilidad.

## Atomic CSS

- Clases que aplican una sola propiedad (`.m-10`, `.text-center`, etc.).  
- Facilita la reutilización y fomenta consistencia.  
- Frameworks como **TailwindCSS** siguen este enfoque.

## Variables de espaciado (Spacing Scale)
Define incrementos regulares (4px, 8px, 16px …) para márgenes y paddings, manteniendo un ritmo visual coherente.

```scss
$spacing-xs: 4px;
$spacing-sm: 8px;
$spacing-md: 16px;
$spacing-lg: 32px;

.card {
  margin-bottom: $spacing-md;
  padding: $spacing-sm;
}
```

## Estructura modular SASS (básica)

Demuestra cómo dividir el código en archivos y usar mixins, variables y nesting.

```scss
// _variables.scss
$color-primario: #3498db;
$color-secundario: #ff00b3ff;
$spacing-base: 1rem;

// _mixins.scss
@mixin flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

// main.scss
@import 'variables';
@import 'mixins';

body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: $color-secundario;
}

.container {
  @include flex-center;
  gap: $spacing-base;
  height: 100vh;

  .card {
    background: white;
    padding: $spacing-base;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);

    h2 {
      color: $color-primario;
      margin-bottom: $spacing-base;
    }

    p {
      font-size: 0.9rem;
      line-height: 1.4;
    }
  }
}
```

## Estructura modular SASS (avanzada)

Amplía el ejemplo anterior incorporando mapas, mixins parametrizados y media queries reutilizables.

```scss
// _variables.scss
$spacing: 1rem;

$colors: (
  "primary": #3498db,
  "secondary": #ff00b3ff,
  "text": #1d1d1dff,
  "bg": #f5f5f5
);

// _mixins.scss
@mixin flex-center($direction: row) {
  display: flex;
  flex-direction: $direction;
  justify-content: center;
  align-items: center;
}

@mixin responsive($breakpoint) {
  @media (max-width: $breakpoint) {
    @content;
  }
}

// _buttons.scss
@mixin button($bg-color, $color: white) {
  background-color: $bg-color;
  color: $color;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

// main.scss
@import 'variables';
@import 'mixins';
@import 'buttons';

body {
  font-family: system-ui, sans-serif;
  margin: 0;
  background-color: map-get($colors, "bg");
  color: map-get($colors, "text");
}

.container {
  @include flex-center(column);
  gap: $spacing;
  min-height: 100vh;
  padding: $spacing;

  header {
    font-size: 2rem;
    color: map-get($colors, "primary");
    margin-bottom: $spacing;
  }

  .card {
    background: white;
    padding: $spacing;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    width: 100%;
    max-width: 400px;

    h2 {
      margin-bottom: 0.5rem;
    }

    p {
      line-height: 1.5;
    }

    button {
      @include button(map-get($colors, "primary"));
      margin-top: $spacing;
    }
  }

  @include responsive(600px) {
    .card {
      width: 90%;
    }
  }
}
```

## Conclusión

- **SASS/SCSS** aporta lógica, modularidad y escalabilidad.  
- Una **arquitectura CSS clara** (BEM + ITCSS + variables + mixins) mejora el trabajo colaborativo.  
- Combinar **preprocesadores** y **variables CSS nativas** ofrece lo mejor de ambos mundos: rendimiento y flexibilidad.

### [Reto 05: Arquitectura de componentes con SASS](reto-05-sass/README.md)

> Reestructurar el CSS de un componente complejo usando SASS/SCSS y la metodología BEM para mejorar su organización y mantenimiento.









