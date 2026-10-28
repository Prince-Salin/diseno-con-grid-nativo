# Anime clásico y filosofía

Proyecto web basado en un diseño **Bento Grid** que combina la estética del anime clásico con conceptos filosóficos como la identidad, la existencia, la conciencia, el destino y la libertad.

Está realizado con HTML5 y CSS3, sin dependencias ni JavaScript. Utiliza CSS Grid nativo, Grid anidado, variables CSS importadas desde otro fichero, CSS Nesting y modo claro/oscuro.

## Estructura del proyecto

```text
Diseño con Grid nativo/
├── index.html
├── README.md
├── design.md
├── css/
│   ├── style.css
│   └── variables.css
└── img/
    ├── Akira.jpg
    ├── Ghost in the Shell.jpg
    └── Evangelion.jpg
```

## Temática

La página conecta anime clásico y filosofía a través de tres áreas:

- **Identidad**, con Akira y la transformación del yo.
- **Existencia**, con Ghost in the Shell y la conciencia.
- **Destino**, con Evangelion y la libertad de elegir.

Las imágenes usadas actualmente son `Akira.jpg`, `Ghost in the Shell.jpg` y `Evangelion.jpg`, y están en `img/`. Se muestran mediante elementos `<img>` en el HTML. Puedes sustituirlas por otras imágenes y actualizar sus rutas `src` en `index.html`.

## Diseño y técnicas

- Grid principal de tres columnas por encima de 700px.
- Grid secundario de dos columnas dentro de cada área.
- Tarjetas de distintos tamaños: una celda, varias filas o una fila completa.
- Diseño responsive: una columna a 700px o menos.
- Variables de tema en `css/variables.css`.
- CSS Nesting, superficies semitransparentes y transición sutil al pasar el ratón por las tarjetas.
- Preferencia de color del sistema con `prefers-color-scheme`.
- Reducción de movimiento con `prefers-reduced-motion`.
- Fuentes Cormorant Garamond y DM Sans desde Google Fonts, configurables en `css/variables.css` y con alternativas del sistema.

## Ejecución

No se necesita instalar nada. Abre `index.html` en un navegador o utiliza Live Server desde Visual Studio Code. Google Fonts requiere conexión a Internet; si quieres cambiar las fuentes, edita `--fuente-texto` y `--fuente-titulos` en `css/variables.css` y actualiza el enlace a Google Fonts del `index.html`. Las fuentes de reserva del sistema se usan sin conexión.

Consulta [design.md](./design.md) para más información sobre el concepto y las decisiones de diseño.
