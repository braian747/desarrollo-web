# Formateo de texto avanzado
*apuntes tomados a partir de [este enlace](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting)*

## Indice
- [Formateo de texto avanzado](#formateo-de-texto-avanzado)
  - [Indice](#indice)
  - [Listas de descripciones](#listas-de-descripciones)
  - [Citas](#citas)
    - [Citas en línea](#citas-en-línea)
  - [Abreviaturas](#abreviaturas)
  - [Marcar la información de contacto](#marcar-la-información-de-contacto)
  - [Superíndice y subíndice](#superíndice-y-subíndice)
  - [Representación del código informático](#representación-del-código-informático)
  - [Marcar horas y fechas](#marcar-horas-y-fechas)
## Listas de descripciones
 El propósito de estas listas es marcar un conjunto de elementos y sus descripciones asociadas, como términos y definiciones, o preguntas y respuestas. Las listas de descripción utilizan un contenedor diferente al de los otros tipos de listas — `<dl>` (*«description list*» o lista de descripciones); además, cada término está envuelto en un elemento `<dt>` («*description term*» o término a describir), y cada descripción está envuelta en un elemento `<dd>` («*description definition*» o definición de descripción). Por ejemplo: 
 ~~~
 <dl>
  <dt>soliloquio</dt>
  <dd>En las obras dramáticas, corresponde a cuando un personaje se habla a sí mismo para representar sus pensamientos o sentimientos internos y, en el proceso, transmitirlos a la audiencia (pero no a otros personajes).</dd>
  <dt>monólogo</dt>
  <dd>En las obras dramáticas, corresponde a cuando un personaje habla de sus pensamientos en voz alta para compartirlos con el público y cualquier otro personaje presente.</dd>
  <dt>aparte</dt>
  <dd>En las obras dramáticas, corresponde a cuando un personaje comparte un comentario solo con la audiencia para dar efecto cómico o dramático. Suele ser un sentimiento, un pensamiento o información adicional.</dd>
</dl>
~~~
## Citas
HTML también dispone de elementos para el marcado de citas; cual elemento utilices depende de si estás marcando la cita como un bloque o como un elemento en línea.

Cita en bloque independiente (blockquote)
Si una sección de contenido a nivel de bloque (ya sea un párrafo, varios párrafos, una lista, etc.) se cita en otro lugar, debes envolverla dentro de un elemento `<blockquote>` para indicarlo, e incluye una URL que apunte a la fuente de la cita dentro de un atributo cite. Por ejemplo:
~~~
<p>A continuación se muestra una cita en bloque independiente...</p>
<blockquote cite="https://developer.mozilla.org/es/docs/Web/HTML/Element/blockquote">
  <p>El <strong>elemento HTML <code>&lt;blockquote&gt;</code></strong> (o <em>elemento HTML de cita
  en bloque independiente</em>) indica que el texto al que delimita es una cita ampliada.</p>
</blockquote>
~~~
### Citas en línea
Las citas en línea funcionan exactamente de la misma manera, excepto que usan el elemento `<q>`. El estilo predeterminado del navegador lo representará como texto normal entre comillas para indicar una cita.

Si deseas que la fuente de la cita esté disponible en la página, lo debes hacer en el texto a través de un enlace o de alguna otra forma apropiada.

## Abreviaturas
Otro elemento bastante común que encontrarás cuando busques en la Web es `<abbr>` — se usa para envolver una abreviatura o acrónimo, y proporcionar una expansión completa del término (incluida dentro de un atributo `title`. La expansión aparecerá en una descripción emergente cuando se coloque el cursor sobre el término.Veamos un par de ejemplos:
~~~
<p>Usamos <abbr title="Lenguaje de marcado de hipertexto">HTML</abbr> para estructurar nuestros documentos web.</p>

<p>Creo que el <abbr title="Reverendo"">Rev.</abbr> Green lo hizo en la cocina con la motosierra.</p>
~~~
## Marcar la información de contacto
HTML tiene un elemento para marcar la información de contacto — `<address>`. Este simplemente envuelve tus datos de contacto, por ejemplo:
~~~
<address>
  <p>Chris Mills, Manchester, The Grim North, Reino Unido</p>
</address>
~~~

## Superíndice y subíndice
En ocasiones, necesitarás utilizar superíndice y subíndice al marcar elementos como fechas, fórmulas químicas y ecuaciones matemáticas para que tengan el significado correcto. Los elementos `<sup>` y `<sub>` se ocupan de ello. Por ejemplo:
~~~
<p>Nací el 25<sup>th</sup> de mayo de 2001.</p>
<p>La fórmula química de la cafeína es C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>.</p>
<p>If x<sup>2</sup> es 9, x debe ser igual 3 o -3.</p>
~~~

## Representación del código informático
Hay una serie de elementos disponibles para marcar código informático usando HTML:

- `<code>`: Para marcar fragmentos genéricos de código informático.
- `<pre>`: Para respetar los espacios en blanco (en general, en los bloques de código) — si utilizas la sangría o diversos espacios en blanco consecutivos dentro de un texto, los navegadores los ignorarán y no se mostrarán en la página. Sin embargo, si delimitas el texto con las etiquetas `<pre></pre>`, los espacios en blanco se representarán de forma idéntica a como se ven en tu editor de texto.
- `<var>`: Para marcar específicamente nombres de variables.
- `<kbd>`: Para marcar entradas de teclado (y de otro tipo) en el ordenador.
- `<samp>`: Para marcar la salida de un programa de ordenador.

## Marcar horas y fechas
HTML también proporciona el elemento <time> para marcar horas y fechas en un formato legible por la máquina. Por ejemplo:

    <time datetime="2022-06-08">08 Junio 2022</time>

El ejemplo básico anterior solo proporciona una fecha simple legible por la máquina, pero hay muchas otras opciones que son posibles, por ejemplo:
~~~
Fecha simple estándar
<time datetime="2016-01-20">20 Enero 2016</time>

Solo año y mes 
<time datetime="2016-01">Enero 2016</time>

Solo mes y día 
<time datetime="01-20">20 Enero 2016</time>

Solo tiempo, horas y minutos
<time datetime="19:30">19:30</time>

¡También puedes hacer segundos y milisegundos! 
<time datetime="19:30:01.856">19:30:01.856</time>

Fecha y hora
<time datetime="2016-01-20T19:30">7.30pm, 20 Enero 2016</time>

Fecha y hora con desplazamiento de zona horaria
<time datetime="2016-01-20T19:30+01:00">7.30pm, 20 Enero 2016 es 8.30pm en Francia</time>

Llamar a un número de semana específico
<time datetime="2016-W04">La cuarta semana de 2016</time>
~~~