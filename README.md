# Estudio Creativo Chinchulín

Portfolio personal desarrollado como parte del curso de Desarrollo Web en Coderhouse. El sitio presenta los servicios de freelance de Camila (landing pages, mantenimiento y branding) y una galería con proyectos reales entregados a clientes.

## Tecnologías utilizadas

- HTML5 semántico
- SCSS (variables, partials, nesting, mixins y `@use`), compilado a un único `style.css`
- Flexbox y CSS Grid con `grid-template-areas`
- Bootstrap 5.3.3 (navbar responsive, carousel)
- Google Fonts (Fraunces + Work Sans)

## Estructura del proyecto

```
├── index.html
├── pages/
│   ├── sobre-mi.html
│   ├── proyectos.html
│   ├── servicios.html
│   └── contacto.html
├── scss/
│   ├── main.scss      (punto de entrada)
│   ├── utilities/
│   │   ├── _variables.scss
│   │   └── _mixins.scss
│   ├── base/
│   │   ├── _base.scss
│   │   └── _tipografia.scss
│   ├── layout/
│   │   ├── _header.scss
│   │   ├── _nav.scss
│   │   ├── _hero.scss
│   │   └── _footer.scss
│   └── components/
│       ├── _buttons.scss
│       ├── _links.scss
│       ├── _cards.scss
│       ├── _carousel.scss
│       └── _forms.scss
├── styles/
│   └── style.css          (compilado, no editar a mano)
└── assets/
    └── img/
```

## Cómo compilar el SCSS

Los estilos se editan en los archivos `.scss` dentro de `scss/`, nunca directamente en `style.css`. Para compilar:

```
npm install -g sass
sass scss/main.scss styles/style.css --style=expanded
```

## Funcionalidades

- Navbar responsive con menú hamburguesa en mobile (Bootstrap)
- Galería de proyectos con carousel (Bootstrap) en Inicio y Proyectos
- Estados `:hover`, `:focus` y `:active` con transiciones en todos los elementos interactivos
- Animación nativa de entrada en el hero (`@keyframes`) y animaciones con la librería AOS en la grilla de servicios y las tarjetas de proyectos
- Diseño mobile-first con CSS Grid y Flexbox, con breakpoints en 768px y 1024px
- Paleta de colores personalizada (soft pink, butter yellow, celeste) aplicada mediante variables funcionales (`$color-primario`, `$color-acento`, `$color-interaccion`)

## Evidencia por criterio de evaluación (SEO, Dominios y Servidores)

Sitio en vivo: https://clase9-zoulalian.netlify.app

**Texto alternativo (20%)**
Todas las imágenes del sitio llevan `alt` descriptivo del contenido real de la foto:
- `index.html` líneas 67 y 75: `alt="Landing page de Studio Ink by Ingrid Muñoz"` / `alt="Landing page de Glow Estética"`.
- `pages/proyectos.html` líneas 54 y 62: mismos `alt` en la galería de proyectos.
El resto de los elementos visuales (íconos del carousel y del navbar) son decorativos de Bootstrap y llevan `aria-hidden="true"` o `aria-label`, no requieren `alt`.

**Contraste (20%)**
Colores definidos en `scss/utilities/_variables.scss`:
- Texto principal `#2E2A45` sobre fondo `#FFFDF7`: contraste 13.46:1 (supera AAA).
- El rosa de acento (`$color-soft-pink`) tiene bajo contraste sobre fondos claros, por eso para links y textos sobre fondo claro se usa `$color-soft-pink-accesible` (mezcla del rosa con el color de texto, definida en la misma línea de variables), que da 4.7:1 sobre fondo claro — cumple WCAG AA. Se usa en `scss/components/_links.scss` línea 15.
- En el header (fondo oscuro `#2E2A45`), el rosa puro sí cumple porque el fondo es oscuro: 4.79:1 (`scss/layout/_nav.scss` líneas 16 y 20).

**SEO on-page (20%)**
- Un solo `<h1>` por página y jerarquía de títulos sin saltos (h1 → h2 → h3) en las 5 páginas.
- HTML semántico: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` en todas las páginas; los `<div>` que quedan son los que exige la estructura de Bootstrap (carousel, cards, grid), no contenedores genéricos evitables.
- Nombres de archivo representativos: `sobre-mi.html`, `proyectos.html`, `servicios.html`, `contacto.html`, `studio-ink.jpg`, `glow-estetica.jpg` (ninguno tipo `IMG_2043.jpg`).

**Meta description (20%)**
Presente en el `<head>` de las 5 páginas, cada una acorde a su contenido:
- `index.html` línea 8, `pages/sobre-mi.html` línea 7, `pages/proyectos.html` línea 7, `pages/servicios.html` línea 7, `pages/contacto.html` línea 7.

**Keywords (20%)**
Cada página tiene su propia `<meta name="keywords">` en el `<head>`, y además las mismas palabras clave están integradas en el contenido visible (no solo en la meta tag), sin repetición forzada ("keyword stuffing"):
- `index.html`: "freelancer", "landing page", "diseño web y desarrollo web" en el hero.
- `pages/sobre-mi.html`: "freelancer", "desarrollo web", "HTML", "CSS", "Box model", "Flexbox" en el texto y la lista de habilidades.
- `pages/proyectos.html`: "portfolio web", "Studio Ink", "Glow Estética" en el texto y las tarjetas.
- `pages/servicios.html`: "landing pages", "mantenimiento", "branding", "identidad visual" en cada tarjeta de servicio.
- `pages/contacto.html`: "landing page", "presupuesto web" en el texto de contacto.

## Autora

Camila Zoulalian
