# Hipervínculos
*apuntes tomados a partir de [este enlace](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)*

## Indice
- [Hipervínculos](#hipervínculos)
  - [Indice](#indice)
  - [Anatomía de un enlace](#anatomía-de-un-enlace)
  - [Añadir información de asistencia con el atributo title](#añadir-información-de-asistencia-con-el-atributo-title)
  - [Convertir bloques de contenido en enlaces](#convertir-bloques-de-contenido-en-enlaces)
  - [URLs y rutas](#urls-y-rutas)
    - [Fragmentos de documento](#fragmentos-de-documento)
    - [URLs absolutas y relativas](#urls-absolutas-y-relativas)
  - [Buenas prácticas en el uso de los enlaces](#buenas-prácticas-en-el-uso-de-los-enlaces)
    - [Redacción clara del enlace](#redacción-clara-del-enlace)
    - [Utiliza enlaces relativos siempre que sea posible](#utiliza-enlaces-relativos-siempre-que-sea-posible)
    - [Indica claramente los recursos no HTML](#indica-claramente-los-recursos-no-html)
    - [Utiliza el atributo download al enlazar una descarga](#utiliza-el-atributo-download-al-enlazar-una-descarga)
  - [Enlace a correo electrónico](#enlace-a-correo-electrónico)
    - [Especificar detalles](#especificar-detalles)

## Anatomía de un enlace
Un enlace básico se crea incluyendo el texto (o cualquier otro contenido), que queramos convertir en un enlace usando un elemento ancla `<a>`, dándole un atributo `href` (también conocido como ***«Hypertext Reference»***, ***«target»*** u ***objetivo***) que contendrá la dirección web hacia dónde queremos que apunte el enlace.
~~~
<p>Crea un enlace a
<a href="https://www.mozilla.org/es-ES/">la página de inicio de Mozilla</a>.
</p>
~~~
Este código producirá el siguiente resultado:

Crea un enlace a la [página de inicio de Mozilla](https://www.mozilla.org/es-ES/).

## Añadir información de asistencia con el atributo title
Otro atributo que posiblemente quieras agregar a tus enlaces es `title`. El título se mostrará al pasar el ratón sobre el texto del enlace.

## Convertir bloques de contenido en enlaces
Como hemos mencionado anteriormente, puedes convertir cualquier contenido en un enlace, incluso Elementos de bloque y elementos en línea. Si quieres convertir una imagen en un enlace, simplemente usa el elemento `<a>` encerrando el elemento `<img>` entre `<a>` y `</a>`.
 ~~~
<a href="https://www.mozilla.org/es-ES/">
  <img src="mozilla-image.png" alt="Logotipo de Mozilla que dirige a la página inicial de Mozilla">
</a>
~~~

## URLs y rutas
### Fragmentos de documento
Es posible apuntar hacia una parte concreta de un documento HTML en vez de a todo un documento. Para ello hay que asignar previamente un atributo `id` al elemento hacia el que apuntamos. Esto se debe hacer en el encabezado y quedará así:

    <h2 id="Dirección_de_envío">Dirección de envío</h2>

Posteriormente para hacer referencia a este `id` concreto, lo añadiremos al final de la URL precedido por una almohadilla — veamos el ejemplo:
~~~
<p>¿Quieres mandarnos una carta? Aquí tienes nuestra
 <a href="contacts.html#Dirección_de_envío">Dirección de envío</a>.</p>
~~~
También podemos usar esta referencia a un fragmento de documento para apuntar hacia otra parte del mismo documento:
~~~
<p>La <a href="#Dirección_de_envío">Dirección de envío de la empresa</a>
 se encuentra al final de esta página.</p>
~~~

### URLs absolutas y relativas
Dos términos que encontrarás en la Web son URL absoluta y URL relativa:

**URL absoluta:** Hace referencia a una dirección definida por su ubicación absoluta en la web, esta incluye el protocolo y el nombre del dominio. Por ejemplo, si subes una página de inicio `index.html` a un directorio llamado `projects` que se encuentra dentro de la raíz de un servidor web, y el dominio del sitio web es `http://www.example.com`, se podrá acceder a la página desde `http://www.example.com/projects/index.html` (o simplemente `http://www.example.com/projects/`, ya que la mayoría de los servidores web buscan la página de inicio `index.html` para cargarla por omisión si no se les especifica otra en la URL).
**URL relativa:** Hace referencia a una dirección que depende de la posición del archivo desde donde se utiliza. Por ejemplo, si desde un archivo ubicado en `http://www.example.com/projects/index.html` queremos enlazar hacia un archivo PDF ubicado en el mismo directorio, la URL sería simplemente el nombre del archivo (por ejemplo: `project-brief.pdf`) no necesitamos más información. Si el archivo PDF está situado en un subdirectorio dentro de `projects` llamado `pdfs`, la URL relativa es: `pdfs/project-brief.pdf`

## Buenas prácticas en el uso de los enlaces

### Redacción clara del enlace
Es fácil rellenar de enlaces una página, sin más. Pero esto no basta. Hay que lograr que nuestros enlaces sean accesibles para todo tipo de lectores, sin importar el contexto o las herramientas que prefieran. Por ejemplo:

- Los usuarios de lectores de pantalla suelen saltar de enlace a enlace en la página y los leen todos sin contexto.
- Los motores de búsqueda utilizan el texto de los enlaces para indizar los archivos buscados, por lo que es una buena idea incluir palabras clave al definir el texto de los enlaces para describir de forma efectiva el sitio al que apuntan.
- Los usuarios visuales suelen echar un vistazo rápido a la página y leen solo lo que les interesa, en lugar de leer todo el texto palabra por palabra, y sus miradas van directamente a las características destacadas de la página, como son los enlaces. Este tipo de usuarios encuentra útiles los textos descriptivos que estos contienen.

**Otras indicaciones:**

- No repetir la URL como parte del texto — Las URLs suenan horrible, y todavía suenan peor si las lee un lector de pantalla, letra por letra.
No escribir «link» o «link a» o «enlace» o «enlace a» en el texto del enlace porque es redundante. Los lectores automáticos indican que hay un enlace al encontrarlo. Los usuarios también saben que hay un enlace, porque normalmente se suele cambiar el color del texto y se subraya (no hay que romper esta convención, porque los usuarios están acostumbrados a ella).
- Redacta la etiqueta del enlace de la manera más breve y concisa posible — los textos de enlace largos son especialmente molestos para los usuarios que utilizan lectores automáticos, porque tienen que escuchar todo el texto del enlace.
- Minimiza los casos en los que varias copias del mismo texto están vinculadas a diferentes lugares. Esto puede causar problemas a los usuarios de lectores de pantalla, si hay una lista de enlaces fuera de contexto que están etiquetados como "haz clic aquí", "haz clic aquí", "haz clic aquí".

### Utiliza enlaces relativos siempre que sea posible
A partir de las indicaciones anteriores podemos llegar a pensar que es mejor utilizar referencias absolutas en todos los casos; después de todo, estas no se rompen cuando la página se traslada como ocurre con las referencias relativas. Sin embargo, debes utilizar enlaces relativos siempre que sea posible cuando enlaces a otras ubicaciones dentro del mismo sitio web. Cuando vinculas a otro sitio web, deberás utilizar un vínculo absoluto.
### Indica claramente los recursos no HTML
Cuando damos referencias a recursos para descargarlos (como documentos en formato PDF o Word) o para reproducirlos (como archivos de audio o vídeo) o que tengan un efecto inesperado (una ventana emergente) hay que indicarlo para no confundir al usuario.

### Utiliza el atributo download al enlazar una descarga
Si queremos hacer referencia a una descarga en lugar de a algo que abra el navegador, disponemos del atributo download para proporcionar un nombre predeterminado al archivo a guardar. Veamos un ejemplo con un enlace a la descarga de la versión para Windows de Firefox:
~~~
<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=es-MX"
   download="firefox-latest-64bit-installer.exe">
  Descarga la última versión de Firefox para Windows (64 bits) (Español, es-MX)
</a>
~~~

## Enlace a correo electrónico
Es posible crear enlaces o botones que, cuando se pulsan, abren un nuevo correo saliente en lugar de enlazar a un recurso o página. Esto se consigue con el elemento ancla `<a>` y el elemento mailto: seguido del esquema de la URL.

En su forma más básica, un enlace mailto: simplemente contiene la dirección de correo electrónico de los destinatarios. Por ejemplo:

    <a href="mailto:nowhere@mozilla.org">Enviar correo electrónico a ninguna parte</a>
### Especificar detalles
Además de la dirección de correo electrónico, puedes proporcionar otra información. De hecho, puedes incluir cualquier campo estándar contenido en el encabezado de cualquier mensaje en la URL mailto que proporciones. Los más utilizados son el «`subject`» (asunto), «`cc`» (con copia a) o «`bcc`» (copia oculta), y «`body`» (cuerpo del mensaje, que no es realmente un campo de la cabecera, pero permite especificar un mensaje breve para el nuevo correo electrónico). Cada campo y su valor se especifican como un argumento de la consulta.

Veamos un ejemplo que incluye estos campos:
~~~
<a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email">
  Enviar un correo electrónico cc, bcc, asunto y cuerpo
</a>
~~~

**Nota:** Los valores de cada campo deben tener la URL codificada, es decir, sin caracteres no imprimibles (caracteres invisibles, tabulaciones, retornos de carro y saltos de página) y espacios con codificación porcentual (%20) Código porciento. También hay que tener en cuenta el uso del signo de interrogación (?) para separar la URL principal de los valores de los campos, y el símbolo ampersand (&) para separar cada campo dentro del enlace `mailto:`. Esta es la notación de consulta URL estándar. 