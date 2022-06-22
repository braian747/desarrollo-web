# Cabecera y Metadatos en HTML
*Apuntes tomados a partir de [este enlace](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)*

El elemento head de un documento HTML es la parte que no se muestra en el navegador cuando se carga la página. Contiene información como el título `(<title>)` de la página, enlaces al CSS (si quieres aplicar estilo a tu contenido HTML con CSS), enlaces para personalizar favicon, y otros metadatos (datos sobre el HTML, como quién lo escribió y palabras claves importantes que describen el documento).
## Indice
- [Cabecera y Metadatos en HTML](#cabecera-y-metadatos-en-html)
  - [Indice](#indice)
  - [Añadir un título](#añadir-un-título)
  - [Metadatos: el elemento `<meta>`](#metadatos-el-elemento-meta)
    - [La codificación de caracteres de tu documento](#la-codificación-de-caracteres-de-tu-documento)
    - [Añadir un autor y descripción](#añadir-un-autor-y-descripción)
    - [Otros tipos de metadatos](#otros-tipos-de-metadatos)
  - [Agregar iconos personalizados a tu sitio](#agregar-iconos-personalizados-a-tu-sitio)
  - [Aplicar CSS y JavaScript a HTML](#aplicar-css-y-javascript-a-html)
  - [Establecer el idioma principal del documento](#establecer-el-idioma-principal-del-documento)

La cabecera HTML es el contenido del elemento `<head>` — a diferencia del contenido del elemento `<body>` (que sí se muestra en la página cuando se carga en el navegador), el contenido de la cabecera no se muestra en la página. Por el contrario, la función de la cabecera es contener los **metadatos** [^metadatos] del documento.
[^metadatos]:Los metadatos son, en su definición más simple, datos que describen otros datos. Por ejemplo, un documento HTML son datos, pero HTML también puede contener metadatos en su elemento `<head>` que describe el documento, como por ejemplo, quién lo escribió y su resumen.

## Añadir un título
El elemento `<title>` se puede usar para poner un título al documento. Sin embargo, esto se puede confundir con el elemento `<h1>`, que se utiliza para poner un encabezado de nivel superior al cuerpo de tu contenido, esto también se conoce como el título de la página. ¡Pero son cosas diferentes!

- El elemento `<h1>` aparece en la página cuando se carga en el navegador — en general debería haber uno solo por página, para especificar el título del contenido de tu página. Se incluye dentro del elemento `<body>`
- El elemento `<title>` es un metadato que representa el título de todo el documento HTML (no del contenido del documento). Se incluye dentro del elemento `<head>`

## Metadatos: el elemento `<meta>`
Los metadatos son datos que describen datos, y HTML tiene una forma «oficial» de introducir metadatos en un documento — el elemento `<meta>`. Por supuesto, el resto de los elementos de los que hablaremos en este artículo también se podrían considerar metadatos. Hay muchos diferentes tipos de elementos `<meta>` que se pueden incluir en el `<head>` de tu página, pero vamos a mencionar solo algunos, para que te hagas una idea.

### La codificación de caracteres de tu documento

    <meta charset="utf-8">

Este elemento simplemente especifica la codificación de caracteres del documento — es decir, el conjunto de caracteres que el documento puede usar. utf-8 es un conjunto de caracteres universal que incluye casi todos los caracteres de casi cualquier idioma humano. Esto significa que tu página web podrá gestionar la visualización de cualquier idioma; por lo tanto, resulta una buena idea configurarlo en cada página web que crees. Por ejemplo, tu página podría gestionar inglés y japonés sin problemas.

### Añadir un autor y descripción
Muchos elementos `<meta>` incluyen atributos `name` y `content`:

`name` especifica el tipo de metadato del que se trata; es decir, qué tipo de información contiene.
`content` especifica el contenido del metadato en sí.
Dos de esos metadatos que resultan útiles de incluir en tu página definen al autor de la página y proporcionan una descripción concisa de la página. Veamos un ejemplo:
~~~
<meta name="author" content="Chris Mills">
<meta name="description" content="El área de aprendizaje de MDN pretende
proporcionar a los recién llegados a la web todo lo que deben
saber para empezar a desarrollar páginas web y aplicaciones web.">
~~~
Especificar un autor resulta ventajoso por diversos motivos: es útil saber quién escribió la página para poder ponerte en contacto con el autor si tienes preguntas sobre el contenido. Algunos sistemas de gestión de contenido tienen herramientas para extraer automáticamente la información del autor de la página y ponerla a disposición para tales fines.

Especificar una descripción que incluya palabras clave relacionadas con el contenido de tu página resulta útil porque tiene el potencial de hacer que la página aparezca más arriba en las búsquedas relevantes que efectúan los motores de búsqueda.

### Otros tipos de metadatos
Al navegar por la web también puedes encontrar otros tipos de metadatos. Muchas de las funciones que verás en los sitios web son creaciones propietarias diseñadas para proporcionar a ciertos sitios (como los sitios de redes sociales) información específica que puedan usar.

Por ejemplo, [Open Graph Data](https://ogp.me/) es un protocolo de metadatos que Facebook inventó para proveer metadatos más ricos para los sitios web. Un efecto de esto es que cuando desde Facebook enlazas a un MDN, el enlace aparece con una imagen y una descripción, lo que resulta en una experiencia más enriquecedora para los usuarios.
Twitter también tiene sus metadatos propios, las [Twitter Cards](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/abouts-cards), que tienen un efecto similar cuando la URL del sitio se muestra en twitter.com.

## Agregar iconos personalizados a tu sitio
Para enriquecer un poco más el diseño de tu sitio puedes añadir en tus metadatos referencias a iconos personalizados, que se mostrarán en determinados contextos. El más común de ellos es el `favicon` (abreviatura de *favorite icon —icono «favorito»*, referido al uso que se le da en las listas de «favoritos» o de marcadores («bookmarks»). Es posible que veas (según el navegador) favicons que se muestran en la pestaña del navegador que contiene cada página abierta y junto a las páginas marcadas en el panel de marcadores.

Para añadir un favicon a tu página:

1. Guárdalo en el mismo directorio que la página index de tu sitio, en formato .ico (la mayoría de los buscadores admiten favicon en los formatos más comunes como .gif o .png, pero usar el formato ICO garantiza que funcionará hasta en Internet Explorer 6.)
2. Añade la siguiente línea de referencia en el <head> de tu HTML:
`<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">`

## Aplicar CSS y JavaScript a HTML
Prácticamente todos los sitios web usan CSS para darles un buen aspecto y JavaScript para añadir funcionalidades interactivas, como reproductores de vídeo, mapas, juegos y demás. La manera más habitual de añadir CSS y JavaScript a una página web es con los elementos `<link>` y el elemento `<script>`, respectivamente.

El elemento `<link>` siempre debe ir dentro del `<header>` de tu documento. Este toma dos atributos, `rel="stylesheet"`, que indica que es la hoja de estilo del documento, y `href`, que contiene la ruta al archivo de la hoja de estilo:

    <link rel="stylesheet" href="my-css-file.css">

El elemento `<script>` también debería ir en el `head`, y debería incluir un atributo `src` con la ruta al JavaScript que quieres cargar, y `defer`, que básicamente le dice al navegador que cargue el JavaScript al mismo tiempo que el HTML de la página. Esto es útil porque hace que todo el HTML se cargue antes de ejecutar el JavaScript, para que no haya errores porque el JavaScript ha intentado acceder a un elemento HTML que todavía no existe. 
    
    <script src="my-js-file.js"></script>
 
**Nota:** El elemento `<script>` puede parecer un elemento vacío pero no lo es, y por lo tanto necesita una etiqueta de cierre. En vez de apuntar a un archivo de `script` externo, también puedes colocar tu código dentro del elemento `<script>`.

## Establecer el idioma principal del documento
Por último, merece la pena mencionar que puedes (y realmente deberías) especificar el idioma de tu página. Esto se puede hacer añadiendo el atributo `lang` a la etiqueta de apertura del HTML 

    <html lang="es-AR">

Esto resulta útil en muchos sentidos. Los motores de búsqueda indizarán tu documento HTML de modo más efectivo si estableces el idioma (permitiendo, por ejemplo, que aparezca correctamente en los resultados del idioma especificado), y resulta útil para que las personas con discapacidad visual que utilizan los lectores de pantalla (por ejemplo, la palabra «six» existe tanto en francés como en inglés, pero su pronunciación es diferente).