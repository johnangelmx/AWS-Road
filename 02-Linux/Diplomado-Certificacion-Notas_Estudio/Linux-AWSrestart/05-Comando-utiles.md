# Comandos Basicos utiles

## whoami

```bash
[username@hostname ~]$ whoami
```

La concatenación de las cadenas who,am y i es whoami. En Linux, se utiliza para mostrar el nombre de usuario del usuario
actual cuando se invoca el comando.

## id

```bash
[username@hostname ~]$ id
```

Este comando ayuda a identificar el nombre de usuario y de grupo y los ID numéricos (UID o ID de grupo) del usuario
actual o de cualquier otro usuario del servidor. Este comando muestra la información de usuario y de grupo de cada
USUARIO especificado o del usuario actual (si se omite el USUARIO.

## hostname

```bash
[username@hostname ~]$ hostname
```

Este comando muestra el nombre de host TCP/IP. El nombre de anfitrión se utiliza para establecer o mostrar el nombre de
anfitrión, dominio o nodo actual del sistema. Muchos programas de red utilizan nombres de host para identificar el
sistema.

## uptime

```bash
[username@hostname ~]$ uptime
```

Este comando indica cuánto tiempo el sistema ha estado encendido desde el último arranque.

## date

```bash
[username@hostname ~]$ date
```

Este comando puede mostrar la hora actual en un formato determinado. También puede establecer la fecha del sistema

## cal

```bash
[username@hostname ~]$ cal
```

El comando cal se utiliza para mostrar un calendario. Si no se especifican argumentos, se muestra el mes actual.

## clear

```bash
[username@hostname ~]$ clear
```

El comando clear se utiliza para borrar la pantalla del terminal. Cuando se ejecuta este comando, se borra todo el texto
de la pantalla del terminal y se muestra un nuevo mensaje

## echo

```bash
[username@hostname ~]$ echo
```

El comando echo coloca el texto especificado en la pantalla. En los scripts, resulta útil proporcionar información a los
usuarios a medida que se ejecuta el script. Dirige el texto seleccionado a la salida estándar o en scripts para
proporcionar descripciones de los resultados mostrados.

## history

```bash
[username@hostname ~]$ history
```

Bash guarda un historial de los comandos de cada usuario en un archivo en el directorio principal de ese usuario. El
comando history muestra el archivo de historial.

- Muestra el archivo de historial del usuario actual.
- Con las teclas de flecha arriba y abajo, se recorre la salida o el archivo de historial.
- Este comando se puede ejecutar mediante un número de evento: por ejemplo, !143.

## touch

```bash
[username@hostname ~]$ touch
```

El comando touch puede utilizarse para crear, cambiar o modificar marcas de tiempo en archivos existentes.  
Además, el comando touch se utiliza para crear un nuevo archivo vacío en un directorio. Para crear un nuevo archivo
mediante el comando touch, ingrese touch file_example_1  
Puede utilizar el comando touch para generar más de un archivo nuevo a la vez, escribiendo la sintaxis touch
file_example_1 file_example_2 file_example_3

## cat

```bash
[username@hostname ~]$ cat
```

El comandocat se utiliza para mostrar el contenido de los archivos. Este comando es útil para los administradores porque
las configuraciones de Linux se guardan en archivos de texto. En el ejemplo que se muestra, puede utilizar este comando
para ver el contenido del archivo hosts.allow.
