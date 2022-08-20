# Trabajando con comandos

En el siguiente apartado conoceremos algunas formas en la cuales podremos ver diferente caracteristicas que podemos
encontrar para manipular la bash

## Uso de comillas Bash

- Comillas Dobles ("): Se utilizan para definir textos y "se expanden". Es decir, las variables dentro de las comillas
  dobles son interpretadas (y no se muestran como el nombre de la variable).
- Comillas Simples ('): Se utilizan para definir textos y "no se expanden". Es decir, las variables dentro de las
  comillas simples se muestran como el nombre de la variable (y no se muestran como su valor).
- Acento Grave (`): Se utilizan para indicar a bash que interprete el comando que hay entre los acentos.

## Metacaracteres Bash

- `*`: Se sustituye por cualquier secuencia de caracteres.
- `?`: Se sustituye por cualquier carácter.
- `[]`: Se utiliza para especificar una lista de caracteres o un rango. Si se quiere especificar un rango se debe ubicar
  el carácter - entre el primer y el último carácter del rango. Se sustituye por un carácter de la lista o del rango.
- `^`: Indica que la expresión comienza al principio de la línea.
- `$`: Indica el final de línea.
- `*` se refiere a cualquier conjunto de caracteres, incluido ningún carácter.
- `z*`: cualquier conjunto de caracteres que empiece por z.
- `*z` cualquier conjunto que acabe en z.
- `[lw]*` cualquier conjunto que empiece por l o w.
- `*[lw]` cualquier conjunto que termine en l o w.
- `[0-9]*` cualquier conjunto que empiece por un dígito.
- `*[0-9]` cualquier conjunto que acabe en un dígito.
- `[a-z]*` cualquier conjunto de caracteres que empiece con una letra minúscula.
- `*[a-z]` cualquier conjunto de caracteres que acabe con una letra minúscula.
- `jo?[am]?.txt` cualquier fichero de texto (.txt) cuyo nombre comience con jo seguido de un carácter cualquiera, a
  continuación el carácter debe ser o unaa a o una m y luego otro carácter cualquiera. joumi.txt encajaría, al igual que
  jotai.txt, por ejemplo.

## Escape y entrecomillado

El carácter \ permite representar en la línea de comandos los caracteres especiales que hemos comentado. Por ejemplo, \*
no representaría cualquier cadena de caracteres sino el carácter \*. En informática se denomina escapar un carácter
especial a este proceso.

Comillas simples, ('). El shell no procesa ni variables ni comandos.

```bash
 echo 'mi espacio es $HOME y mi ordenador se llama hostname'
 mi espacio es $HOME y mi ordenador se llama hostname
```

Comillas dobles, ("). El shell procesa y expande las variables pero no los comandos.

```bash
 echo "mi espacio es $HOME y mi ordenador se llama hostname"
 mi espacio es /home/spock y mi ordenador se llama hostname
```

Backticks, (`). El shell intenta procesar cada palabra entre comillas como un comando. Si hay variables, se evalúan
primero y luego se procesan como un comando.

```bash
 echo `mi espacio es $HOME y mi ordenador se llama hostname`
 mi espacio es /home/spock y mi ordenador se llama Vulcano
```

## Otros caracteres especiales

Existen otros caracteres que tienen significado especial, además de los ya mencionados.

- `|`: Se usa para las listas de tuberías como hemos visto anteriormente.
- `>` y `>>`: Para redirigir la salida estándar.
- `~`: Se sustituye por el directorio base del usuario que lo ejecuta.
  Ejemplo: ls ~/pruebas/ejercicio1 es equivalente a ls /home/nombre_usuario/pruebas/ejercicio1.
- `$`: Se utiliza para obtener el valor de una variable.
  Ejemplo: Primero as ignamos un valor a una variable, utilizando =, config_apache=/etc/httpd/httpd.conf. Ahora podremos
  acceder a ese archivo utilizando config_apache, cat $config_apache, la ejecución de este comando imprime el contenido
  del archivo por el terminal..
- `$((expresión))`: Se evalúa la expresión y se sustituye en la línea original por el resultado de la misma.

## noclobber

Un pequeño tip donde aprendemos a evitar la escritura accidental en GNU/Linux con noclobber. Para conseguirlo, solo
debemos exportar el valor «noclobber» a las variables de la sesión de la shell de BASH

Como sabemos para enviar la salida standard a otro fichero lo haríamos como sigue:

```bash
comando > fichero.txt
```

Está claro que, si en ese fichero tenemos información importante, que otra persona o nosotros mismos, por error,
enviamos información con stdout «>«, podemos tener un grave problema. Para evitarlo debemos declarar el valor
«noclobber» en la sesión de la shell.

De esta manera indicaremos a shell de BASH, que no elimine datos ni contenidos de archivos por error.

## Expresiones regulares grep, awk y otros filtros

Las expresiones regulares permiten definir patrones de texto utilizando los metacaracteres. Estos patrones se pueden
utilizar entre otras cosas para hacer búsquedas, extraer información o hacer sustituciones.

El comando grep devuelve las líneas o archivos que se ajustan a un patrón de búsqueda especificado. El patrón de
búsqueda se puede realizar con metacaracteres tanto en las expresiones como en la lista de nombres de ficheros.

La sintaxis es la siguiente:  
grep opciones expresión ficheros
Para buscar más de una palabra se separan con caracteres en blanco, o bien se usan caracteres comodín. Debe encerrar la
expresión entre comillas.
Algunas de las las opciones del comando grep son:

- `-v` las líneas que no coinciden con la expresión.
- `-l` los nombres de los ficheros pero no las líneas.
- `-i` las coincidencias sin diferenciar entre mayúsculas y minúsculas.
- `-n` el número de la línea donde hay coincidencia
  El comando awk nos permite aplicar una acción sobre las líneas que se ajusten a un patrón definido. Las líneas pueden
  proceder de un fichero o de la entrada estándar.

El patrón puede ser entre otras cosas:

- Un patrón de texto. Se comprueba en el texto qué líneas se ajustan a este patrón. Debe colocarse entre barras.
- Una expresión. Se comprueba en qué líneas del texto la expresión se cumple (se hace verdadera).
  Para realizar operaciones que normalmente haríamos con un editor de textos (sustituir palabras, mover bloques, etc) se
  puede usar sed , que es un editor de textos no interactivo

Existen otros comandos a los que se denomina filtros por actuar de modo no interactivo, entre los que se encuentran:

- sort:

**sort** fichero ordena las líneas según el código ASCII. Ejemplo: pruébese ls|sort.  
**sort** -n fichero ordena numéricamente.

- find:

Este comando explora una rama de directorios (camino o path) buscando ficheros que cumplan determinados criterios. Opera
recursivamente, así que si se indica que busque en / extenderá sus pesquisas a todo el sistema de ficheros. Esto puede
ser lento. Se pueden emplear los siguientes criterios de búsqueda:

- El nombre se ajusta un patrón: find camino -name patrón. Ejemplo: find /tmp -name \*.txt.
- Última fecha de acceso o modificación: find camino -atime.
- Tamaño find camino -size.
- No tienen contenido: find camino -empty.
- wc: Cuenta líneas wc -l, palabras wc -w o caracteres wc -c.
