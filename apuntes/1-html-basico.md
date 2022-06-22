# Conceptos básicos de HTML
*Apuntes tomados a partir de [este enlace](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/Getting_started)*

HTML no es un lenguaje de programación; es un lenguaje de marcado que define la estructura de tu contenido. HTML consiste en una serie de elementos que usarás para encerrar diferentes partes del contenido para que se vean o comporten de una determinada manera.

## Indice
- [Conceptos básicos de HTML](#conceptos-básicos-de-html)
  - [Indice](#indice)
  - [Anatomia de un elemento HTML](#anatomia-de-un-elemento-html)
  - [Atributos](#atributos)
  - [Atributos booleanos](#atributos-booleanos)
  - [Elementos anidados](#elementos-anidados)
  - [Elementos de bloque y elementos en línea](#elementos-de-bloque-y-elementos-en-línea)
  - [Elementos vacíos](#elementos-vacíos)
  - [Anatomía de un documento HTML](#anatomía-de-un-documento-html)
  - [Imagenes](#imagenes)
  - [Referencias a entidades: Inclusión de caracteres especiales en HTML](#referencias-a-entidades-inclusión-de-caracteres-especiales-en-html)
  - [Marcado de texto](#marcado-de-texto)
    - [Encabezados](#encabezados)
    - [Parrafos](#parrafos)
    - [Listas](#listas)
    - [Vinculos](#vinculos)
  - [Comentarios HTML](#comentarios-html)

## Anatomia de un elemento HTML
![](https://mdn.mozillademos.org/files/11913/htmlexp.png)

Las partes principales del elemento son:

**1. La etiqueta de apertura:** consiste en el nombre del elemento (en este caso, p), encerrado por paréntesis angulares (< >) de apertura y cierre. Establece dónde comienza o empieza a tener efecto el elemento —en este caso, dónde es el comienzo del párrafo—.
**2. La etiqueta de cierre:** es igual que la etiqueta de apertura, excepto que incluye una barra de cierre (/) antes del nombre de la etiqueta. Establece dónde termina el elemento —en este caso dónde termina el párrafo—.
**3. El contenido:** este es el contenido del elemento, que en este caso es sólo texto.
**4. El elemento:** la etiqueta de apertura, más la etiqueta de cierre, más el contenido equivale al elemento.

## Atributos
![](https://mdn.mozillademos.org/files/11915/htmlatributos.png)

Los atributos contienen información adicional acerca del elemento, la cual no quieres que aparezca en el contenido real del elemento. Aquí class es el nombre del atributo y editor-note el valor del atributo. En este caso, el atributo class permite darle al elemento un nombre identificativo, que se puede utilizar luego para apuntarle al elemento información de estilo y demás cosas.

Un atributo debe tener siempre:

- Un espacio entre este y el nombre del elemento (o del atributo previo, si el elemento ya posee uno o más atributos).
- El nombre del atributo, seguido por un signo de igual (=).
- Comillas de apertura y de cierre, encerrando el valor del atributo.

## Atributos booleanos
En ocasiones puedes ver atributos escritos sin valor. Esto está permitido. Estos se denominan atributos booleanos. Los atributos booleanos solo pueden tener un valor, que generalmente es el mismo que el nombre del atributo. Por ejemplo:
`<input type="text" disabled="disabled">`

De manera abreviada, también es posible escribirlo como se describe a continuación:
`<input type="text" disabled>`
## Elementos anidados
Se pueden poner elementos dentro de otros elementos. Esto se llama **anidamiento**. Si quisiéramos decir que nuestro gato es muy gruñón, podríamos encerrar la palabra muy en un elemento `<strong>` para que aparezca destacada.

`<p>Mi gato es <strong>muy</strong> gruñón.</p>`

Hay una forma correcta e incorrecta de anidar. En el ejemplo anterior, primero abrimos el elemento p, luego abrimos el elemento strong. Para un anidamiento adecuado, primero debemos cerrar el elemento strong, antes de cerrar el p.

## Elementos de bloque y elementos en línea
Hay dos categorías importantes de elementos en HTML — Estos son los elementos de bloque y los elementos en línea.

- Los elementos de bloque forman un bloque visible en la página. Aparecerán en una línea nueva después de cualquier contenido anterior. Cualquier contenido que vaya después también aparecerá en una línea nueva. Los elementos a nivel de bloque suelen ser elementos estructurales de la página. Por ejemplo, un elemento a nivel de bloque puede representar encabezados, párrafos, listas, menús de navegación o pies de página. Un elemento a nivel de bloque no estaría anidado dentro de un elemento en línea, pero podría estar anidado dentro de otro elemento a nivel de bloque.
- Los elementos en línea están contenidos dentro de elementos de bloque y delimitan solo pequeñas partes del contenido del documento; (no párrafos enteros o agrupaciones de contenido) Un elemento en línea no hará que aparezca una nueva línea en el documento. Suele utilizarse con texto. Por ejemplo es el caso de un elemento `<a>` (hipervínculo) o elementos de énfasis como `<em>` o `<strong>`.

## Elementos vacíos
Algunos elementos no poseen contenido, y son llamados elementos vacíos. Toma, por ejemplo, el elemento `<img>` de nuestro HTML:

    <img src="images/firefox-icon.png" alt="Mi imagen de prueba">
Posee dos atributos, pero no hay etiqueta de cierre `</img>` ni contenido encerrado. Esto es porque un elemento de imagen no encierra contenido al cual afectar. Su propósito es desplegar una imagen en la página HTML, en el lugar en que aparece.

## Anatomía de un documento HTML
~~~
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Mi pagina de prueba</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="Mi imagen de prueba">
  </body>
</html>
~~~

- `<!DOCTYPE html>` — el tipo de documento. Es un preámbulo requerido. Anteriormente, cuando HTML era joven (cerca de 1991/2), los tipos de documento actuaban como vínculos a un conjunto de reglas que el código HTML de la página debía seguir para ser considerado bueno, lo que podía significar la verificación automática de errores y algunas otras cosas de utilidad. Sin embargo, hoy día es simplemente un artefacto antiguo que a nadie le importa, pero que debe ser incluido para que todo funcione correctamente.
- `<html></html>` — Este elemento encierra todo el contenido de la página entera y, a veces, se le conoce como el elemento raíz (root element).
- `<head></head>` —  Este elemento actúa como un contenedor de todo aquello que quieres incluir en la página HTML que no es contenido visible por los visitantes de la página. Incluye cosas como palabras clave (keywords), una descripción de la página que quieres que aparezca en resultados de búsquedas, código CSS para dar estilo al contenido, declaraciones del juego de caracteres, etc.
- `<meta charset="utf-8">` —  Este elemento establece el juego de caracteres que tu documento usará en utf-8, que incluye casi todos los caracteres de todos los idiomas humanos. Básicamente, puede manejar cualquier contenido de texto que puedas incluir. No hay razón para no establecerlo, y puede evitar problemas en el futuro.
- `<title></title>` — establece el título de tu página, que es el título que aparece en la pestaña o en la barra de título del navegador cuando la página es cargada, y se usa para describir la página cuando es añadida a los marcadores o como favorita.
- `<body></body>` —  Encierra todo el contenido que deseas mostrar a los usuarios web que visiten tu página, ya sea texto, imágenes, videos, juegos, pistas de audio reproducibles, y demás.

## Imagenes
`<img src="images/firefox-icon.png" alt="Mi imagen de prueba">`

Este elemento incrusta una imagen en la página, en la posición en que aparece. Lo logra a través del atributo *src* (source), el cual contiene el path (ruta o ubicación) de tu archivo de imagen.

También se incluye un atributo *alt* (alternative) el cual contiene un texto que debería describir la imagen, y que podría ser accedido por usuarios que no pueden ver la imagen

## Referencias a entidades: Inclusión de caracteres especiales en HTML
En HTML, los caracteres <, >,",' y & son caracteres especiales. Forman parte de la sintaxis HTML. Entonces, ¿cómo incluye uno de estos caracteres especiales en tu texto? Por ejemplo, si deseas utilizar un signo comercial o menor que, y no hacer que se interprete como código.

Haces esto con referencias de caracteres. Estos son códigos especiales que representan caracteres, para ser usados en estas circunstancias exactas. Cada referencia de caracter comienza con un signo de ampersand (&) y finaliza con un punto y coma ( ; ).
|  Caracter literal |  Equivalente de referencia de caracteres |
|---|---|
|  < | \&lt;   |
| >  | \&gt;   |
| "  | \&quot; |
| '  | \&apos; |
| &  | \&amp;  |


## Marcado de texto

### Encabezados
Los elementos de encabezado permiten especificar que ciertas partes del contenido son encabezados, o subencabezados del contenido. HTML posee seis niveles de encabezados (`<h1> - <h6>`)

### Parrafos
los elementos `<p>` se utilizan para encerrar párrafos de texto
`<p>Este es un simple parrafo</p>`

### Listas
Mucho del contenido web está dado por listas, así que HTML tiene elementos especiales para ellas. El marcado de listas se realiza siempre en al menos dos elementos. Los dos tipos de listas más comunes son las listas ordenadas y las desordenadas:

- Las listas desordenadas son aquellas en las que el orden de los items no es relevante, como en una lista de compras. Estas son encerradas en un elemento `<ul>` (unordered list).
- Las listas ordenadas son aquellas en las que el orden sí es relevante, como en una receta. Estas son encerradas en un elemento `<ol>` (ordered list).
Cada elemento de la lista se coloca dentro de un elemento `<li>` (list item).
por ejemplo:
~~~
<p>En Mozilla, somos una comunidad de</p>

<ul>
  <li>tecnólogos</li>
  <li>pensadores</li>
  <li>constructores</li>
</ul>

<p>trabajando juntos... </p>
~~~
### Vinculos
Para implementar un vínculo, necesitas usar un vínculo simple — `<a>` — la a es la abreviatura de la palabra inglesa «anchor» («ancla»). Para convertir algún texto dentro de un párrafo en un vínculo, sigue estos pasos:

1. Elige algún texto. Nosotros elegimos «Manifesto Mozilla».

2. Encierra el texto en un elemento `<a>`, así:
`<a>Manifesto Mozilla</a>`

3. Proporciónale al elemento `<a>` un atributo href *(**h**ypertext **ref**erence)*, así:
`<a href="">Manifesto Mozilla</a>`

4. Completa el valor de este atributo con la dirección web con la que quieras conectar al vínculo:
`<a href="https://www.mozilla.org/es-AR/about/manifesto/">Manifesto Mozilla</a>`

Podrías obtener resultados inesperados si al comienzo de la dirección web omites la parte `https://` o `http://` llamada protocolo. Así que luego del marcado del vínculo, haz clic en él para asegurarte que te dirige a la dirección deseada.

## Comentarios HTML
Para convertir en un comentario una sección de contenido de tu archivo HTML, debes delimitarlo con los marcadores especiales `<!-- y -->`. Por ejemplo:
`<!-- esto es un comentario, no se veria en la pagina web -->`