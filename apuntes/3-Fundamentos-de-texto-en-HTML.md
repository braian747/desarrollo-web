# Fundamentos de texto en HTML
*apuntes tomados a partir de [este enlace](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)*

Una de las principales funciones de HTML es dar al texto estructura y significado (también conocido como semántica), de forma que un navegador pueda mostrarlo correctamente. Este articulo explica la forma en que se puede usar HTML para estructurar una página de texto añadiendo encabezados y párrafos, enfatizando palabras, creando listas y más.

## Indice
- [Fundamentos de texto en HTML](#fundamentos-de-texto-en-html)
  - [Indice](#indice)
  - [Encabezados y párrafos](#encabezados-y-párrafos)
    - [Cómo establecer la estructura jerárquica](#cómo-establecer-la-estructura-jerárquica)
  - [Listas](#listas)
    - [Listas no ordenadas](#listas-no-ordenadas)
    - [Listas ordenadas](#listas-ordenadas)
    - [Listas anidadas](#listas-anidadas)
  - [Énfasis e importancia](#énfasis-e-importancia)
    - [Énfasis](#énfasis)
    - [Importancia fuerte](#importancia-fuerte)
    - [Cursiva, negrita, subrayado...](#cursiva-negrita-subrayado)

## Encabezados y párrafos
El contenido estructurado simplifica la experiencia en la lectura y se disfruta más.

En HTML, cada párrafo tiene que estar delimitado por un elemento `<p>`. Cada sección tiene que estar delimitada por un elemento de encabezado `<h1>...<h6>`, donde cada elemento representa un nivel de contenido diferente en el documento; `<h1>` representa el título principal, `<h2>` representa el subtítulo, `<h3>` representa el subtítulo del subtítulo, y así sucesivamente.

### Cómo establecer la estructura jerárquica
- Preferentemente debes usar solo un `<h1>` por página; este es el nivel de título superior, y todos los demás se sitúan por debajo de él en la jerarquía.
- Asegúrate de que usas los títulos en el orden correcto en la jerarquía. No uses los `<h3>` para representar subtítulos, seguidos de los `<h2>` para representar los subtítulos de los subtítulos; eso no tiene sentido y provocará resultados extraños.
- De los seis niveles de títulos disponibles, debes procurar no usar más de tres por página, a menos que creas que es realmente necesario. Los documentos con muchos niveles (es decir, una jerarquía de títulos muy profunda) son de difícil manejo y navegación. En esos casos se recomienda, si es posible, separar el contenido en varias páginas.

## Listas
 Las listas están en todos lados en la web, y hay tres diferentes tipos de las que nos vamos a ocupar.
 ### Listas no ordenadas
Las listas no ordenadas se usan para marcar listas de artículos cuyo orden no es importante. comienza con un elemento `<ul>` (*«unordered list»*) que delimita todos los elementos de la lista.
### Listas ordenadas
Las listas ordenadas son aquellas en las que el orden de los elementos sí importa. La estructura de marcado es la misma que para las listas no ordenadas, excepto que debes delimitar los elementos de la lista con una etiqueta `<ol>` (*«ordered list»*), en lugar de `<ul>`.

En ambos casos, el siguiente paso es delimitar cada artículo de la lista con un elemento `<li>` (*«list item»*).

### Listas anidadas
Es perfectamente correcto anidar una lista dentro de otra. Posiblemente quieras tener subelementos bajo elementos de rango superior. Por ejemplo, en la siguiente lista de una receta, puesto que los dos últimos elementos están estrechamente relacionados con el elemento anterior (se leen como subinstrucciones u opciones que encajan bajo ese elemento), puede tener sentido anidarlos dentro de su propia lista no ordenada e introducir esa lista bajo el cuarto elemento. Tendría el siguiente aspecto:
~~~
<ol>
  <li>Pela el ajo y picarlo en trozos gruesos.</li>
  <li>Retira las semillas y el tallo del pimiento, y cortarlo en trozos gruesos.</li>
  <li>Mete todos los alimentos en un procesador de alimentos.</li>
  <li>Procesa todos los ingredientes hasta conseguir una pasta.
    <ul>
      <li>Si deseas un hummus "grueso", procésalo corto tiempo.</li>
      <li>Pica durante más tiempo si se desea obtener un hummus "suave".</li>
    </ul>
  </li>
</ol>
~~~
## Énfasis e importancia
### Énfasis
Cuando queremos dar énfasis al lenguaje hablado, *acentuamos* ciertas palabras y así alteramos sutilmente el significado de lo que decimos. De manera similar, en el lenguaje escrito ponemos palabras en cursiva para destacarlas. 
En HTML usamos el elemento `<em>` (*«emphasis»*) para marcar estos casos. El documento logra entonces transmitir una lectura más interesante y además así lo reconocen los lectores de pantalla, que lo expresan con un diferente tono de voz.
### Importancia fuerte
Para enfatizar palabras importantes al hablar solemos acentuarlas, y al escribir lo hacemos en estilo **negrita**.
En HTML usamos el elemento `<strong>` (importancia fuerte) para marcar tales expresiones. El documento resulta entonces más útil, y de nuevo los lectores de pantalla reconocen estos elementos y el tono de voz cambia a uno más fuerte.

En el siguiente ejemplo puede verse la aplicacion de los elementos `<em>` y `<strong>`:
~~~
<p>Este líquido es <strong>altamente tóxico</strong> —
si lo bebes, <strong>podrías <em>morir</em></strong>.</p>
~~~
### Cursiva, negrita, subrayado...
Los elementos que hemos comentado hasta ahora tienen asociada una semántica clara. La situación con `<b>` (negrita o «<b>bold</b>»), `<i>` (cursiva o «<i>italic</i>») y `<u>` (subrayado o «<u>underline</u>») es algo más complicada. Surgieron para que las personas pudieran escribir textos en negrita, cursiva o subrayado en un tiempo en el que pocos navegadores o ninguno admitían el CSS. Elementos como estos, que solo afectan a la presentación y no a la semántica, se conocen como elementos de presentación y no se deberían usar porque, como hemos visto, la semántica es muy importante para la accesibilidad y el SEO, entre otros aspectos.
