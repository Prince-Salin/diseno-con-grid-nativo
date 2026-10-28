# Design — Anime clásico y filosofía

## 1. Concepto

El diseño combina la estética del anime clásico con preguntas sobre identidad, existencia, conciencia, destino y libertad. La composición Bento representa estos conceptos mediante tarjetas modulares.

## 2. Estructura principal

La página se organiza en tres áreas temáticas:

1. **Identidad** — Akira, el yo y la transformación.
2. **Existencia** — Ghost in the Shell, el cuerpo, la memoria y la conciencia.
3. **Destino** — Evangelion, la libertad y las consecuencias de elegir.

Cada área contiene un Grid secundario con una tarjeta visual y tarjetas de contenido.

## 3. Bento Grid y Grid anidado

Por encima de 700px, el Grid principal tiene tres columnas iguales, una por área. Cada área contiene un segundo Grid de dos columnas. La tarjeta visual ocupa dos filas, la tarjeta de reflexión ocupa toda la fila y las demás tarjetas ocupan una celda.

```css
.bento {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
}

.area__grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
}

.item--alto { grid-row: span 2; }
.item--ancho { grid-column: 1 / -1; }
```

Así se combinan celdas individuales con celdas que ocupan varias filas o toda una fila.

## 4. Responsive Design

Por encima de 700px se muestran las tres áreas en columnas. A 700px o menos se apilan en una columna:

```css
@media (max-width: 700px) {
    .bento { grid-template-columns: 1fr; }
}
```

## 5. Imágenes

Las imágenes de las tres áreas están en `img/`: `Akira.jpg`, `Ghost in the Shell.jpg` y `Evangelion.jpg`. Sus rutas se pueden cambiar en los elementos `<img>` de `index.html`. `object-fit: cover` adapta las imágenes a sus tarjetas; no se utiliza `background-image`.

## 6. Color y superficies

Las tarjetas utilizan superficies semitransparentes y `backdrop-filter` de forma discreta. El tema claro parte de tonos cálidos inspirados en el papel impreso. El modo oscuro adopta tonos negros, grises y morados, y se activa automáticamente con `prefers-color-scheme: dark`.

## 7. Tipografía y variables

Cormorant Garamond se utiliza en titulares y preguntas; DM Sans, en los textos generales. Ambas son familias disponibles en Google Fonts y se cargan desde el enlace del `index.html`. Las variables `--fuente-titulos` y `--fuente-texto` de `css/variables.css` permiten cambiarlas; incluyen alternativas del sistema para cuando no haya conexión.

Los colores, espaciados, bordes y sombras están definidos en `css/variables.css`, que se importa desde `css/style.css`. El CSS Nesting agrupa los estilos relacionados de cada área.

## 8. Movimiento y accesibilidad

Las tarjetas tienen una transición breve y una elevación sutil al pasar el puntero. `prefers-reduced-motion` reduce la transición para las personas que lo soliciten en su sistema. Las ilustraciones tienen texto alternativo y la estructura usa encabezados semánticos.

## 9. Objetivo académico

El proyecto demuestra CSS Grid principal y anidado, Bento Grid, tamaños de celda diferentes, media queries, variables CSS importadas desde otro archivo, CSS Nesting, `prefers-color-scheme`, superficies tipo cristal, transición hover, imágenes HTML y diseño adaptable.
