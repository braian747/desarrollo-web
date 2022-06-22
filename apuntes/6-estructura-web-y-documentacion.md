# Estructura web y documentación
*apuntes tomados a partir de [este enlace](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)*

## Indice
- [Estructura web y documentación](#estructura-web-y-documentación)
  - [Indice](#indice)
  - [Partes básicas de un documento](#partes-básicas-de-un-documento)
  - [HTML para dar estructura al contenido](#html-para-dar-estructura-al-contenido)
  - [Elementos de diseño HTML en detalle](#elementos-de-diseño-html-en-detalle)
  - [Saltos de línea y líneas horizontales](#saltos-de-línea-y-líneas-horizontales)
## Partes básicas de un documento
- **Encabezado:** Normalmente formado por una gran franja que cruza la parte superior de la página con un gran título, un logotipo y quizás un lema. Esta parte suele permanecer invariable mientras navegas entre las páginas de un mismo sitio web.
- **Barra de navegación:** Son los enlaces a las secciones principales del sitio web. Normalmente está formada por un menú con botones, enlaces o pestañas. Al igual que el encabezado, este contenido suele permanecer invariable en las diferentes páginas del sitio; tener un menú inconsistente en tu página web conducirá a los usuarios a la confusión y frustración.
- **Contenido principal**: Es la gran parte central de la página y contiene la mayor parte del contenido particular de una página web concreta; por ejemplo, el video que quieres ver, la narración que quieres leer, el mapa que quieres consultar, los titulares de las noticias, etc.
- **Barra lateral:** Suele incluir algún tipo de información adicional, enlaces, citas, publicidad, etc. Normalmente está relacionada con el contenido principal de la página, pero en otras ocasiones encontraras elementos recurrentes como un menú de navegación secundario.
- **Pie de página:** Es la parte inferior de la página, que generalmente contiene la letra pequeña, el copyright o la información de contacto. Es el sitio donde se coloca la información común (al igual que en el encabezado), pero esta información no suele ser tan importante o es secundaria con respecto a la página en sí misma.

## HTML para dar estructura al contenido
HTML dispone de etiquetas adecuadas que puedes usar para establecer estas secciones semánticas, por ejemplo:

encabezado: `<header>`.
menú de navegación : `<nav>`.
contenido principal: `<main>`, con varias subsecciones (además de la barra lateral) representadas por los elementos `<article>`, `<section>`, y `<div>`.
barra lateral: `<aside>`; a menudo colocada dentro de `<main>`.
pie de página: `<footer>`.

## Elementos de diseño HTML en detalle

- `<main>` encierra el contenido particular a esta página. Utilizaremos `<main>` solamente una vez para cada página y lo situaremos directamente dentro del elemento `<body>`. Es mejor que no lo anidemos en otros elementos.
- `<article>` encuadra un bloque de contenido que tiene sentido por sí mismo aparte del resto de la página (por ejemplo una entrada en un blog).
- `<section>` es parecido al elemento `<article>`, pero se usa más para agrupar cada parte de la página que, por su funcionalidad, constituye una sección en sí misma (por ejemplo un minimapa o un conjunto de titulares y resúmenes). Se considera una buena práctica comenzar cada una de estas secciones con un título de encabezado (heading); observa que podemos subdividir artículos (`<article>`) en distintas secciones (`<section>`), o también secciones en distintos artículos, dependiendo del contexto.
- `<aside>` incluye contenido que no está directamente relacionado con el contenido principal, pero que puede aportar información adicional relacionada indirectamente con él (resúmenes, biografías del autor, enlaces relacionados, etc.).
- `<header>` representa un grupo de contenido introductorio. Si este es «hijo» de un elemento `<body>`, se convertirá en el encabezado principal del sitio web, pero si es hijo de un elemento `<article>` o un elemento `<section>`, entonces simplemente será el encabezado particular de cada sección (por favor, no lo confundas con títulos y encabezados).
- `<nav>` contiene la funcionalidad de navegación principal de la página. Los enlaces secundarios, etc., no entrarán en la navegación.
- `<footer>` representa un grupo de contenido al final de una página.

## Saltos de línea y líneas horizontales
Dos elementos que debes conocer y utilizarás ocasionalmente son `<br>` y `<hr>`:

El elemento `<br>` genera un salto de línea en un párrafo; es la única manera de representar series de líneas cortas, como una dirección postal o un poema. Sin el elemento `<br>`, todo el párrafo se habría presentado como una sola línea larga.
Los elementos `<hr>` generan una regla horizontal en el documento que denota un cambio en la temática del texto (como un cambio de tema o de escena). Visualmente tiene el aspecto de una línea horizontal. Por