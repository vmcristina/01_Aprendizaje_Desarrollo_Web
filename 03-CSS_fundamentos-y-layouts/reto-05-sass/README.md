# Reto 05: Arquitectura de Componentes con SASS

## Descripción

Estructurar un CSS usando **SASS/SCSS** y la metodología **BEM**, con el objetivo de lograr un código **modular, reutilizable y fácil de mantener**.  

Este reto busca mejorar la **organización, reutilización y mantenimiento** del CSS mediante **buenas prácticas y herramientas modernas**.

## Objetivos

- Modularizar el CSS usando **archivos parciales** (`partials`) y un archivo principal que los importe.  
- Definir **variables** y **mixins** en SASS para estilos reutilizables y consistentes.  
- Aplicar **anidamiento** para simplificar la escritura de selectores relacionados.  
- Utilizar la **metodología BEM** para nombrar bloques, elementos y modificadores.  
- Usar **mixins con `@include`** y **operadores matemáticos** para cálculos dinámicos en estilos.  

## Acciones realizadas

- Creé una **estructura de archivos SASS** con `styles.scss` como archivo principal y los parciales:  
  - `_variables.scss`  
  - `_mixins.scss`  
  - `_componente-tarjeta.scss`  
- Definí **variables globales** (`$color-principal`, `$color-secundario`, etc.).  
- Implementé **mixins** para efectos comunes (por ejemplo, sombras o media queries).  
- Apliqué **anidamiento** en el componente `.profile-card` y sus elementos hijos (`.profile-card__avatar`, `.profile-card__bio`, etc.).  
- Añadí **modificadores BEM** con clases como `.profile-card--dark` y `.profile-card__button--disabled` usando la sintaxis `&--modificador`.  
- Usé `@include` y **operadores matemáticos** para definir dimensiones dinámicas (`$base * 1.5`).  

## Referencias útiles

- [Sass Basics](https://sass-lang.com/guide)  
- [BEM Methodology](http://getbem.com/introduction/)  
- [Sass Mixins](https://sass-lang.com/documentation/at-rules/mixin)  
- [CSS-Tricks: Using Sass’s Ampersand](https://css-tricks.com/the-sass-ampersand/)  

## Archivos principales

- `index.html`
- `styles.css`
- `styles.scss`
- `_variables.scss`
- `_mixins.scss`
- `_componente-tarjeta.scss`

