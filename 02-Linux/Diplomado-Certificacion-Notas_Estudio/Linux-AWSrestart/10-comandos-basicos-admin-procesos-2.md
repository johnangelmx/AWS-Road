# Comando basico para administracion de procesos

## Comando jobs

Podemos ver un listado de los programas que están ejecutándose en segundo plano, junto con los suspendidos (detenidos),
lanzando el comando interno jobs:

```bash
$ jobs
[1]   Ejecutando              gedit &
[2]-  Detenido                sleep 50
[3]+  Detenido                find / -name Descargas 2> /dev/null
```

La información que se nos muestra es el número de trabajo, el estado (Ejecutando o Detenido) y el comando.

Algunas opciones de jobs son:

- -l Muestra el PID además de la información anterior.
- -p Solo muestra el PID de los trabajos
- -r Solo muestra los trabajos que están en estado de ejecución.
- -s Solo muestra los trabajos que están en estado de detenido.

```bash
$ jobs -l
[1]   4229 Ejecutando              gedit &
[2]-  4239 Parado                  sleep 50
[3]+  4241 Parado                  find / -name Descargas 2> /dev/null
$ jobs -p
4229
4239
4241
$ jobs -r
[1]   Ejecutando              gedit &
$ jobs -s
[2]-  Detenido                sleep 50
[3]+  Detenido                find / -name Descargas 2> /dev/null
```

El comando jobs solo nos muestra los trabajo vinculados a la terminal desde donde se ejecuta jobs, es decir, no nos
mostrará aquellos trabajos que hayan sido lanzados desde otras terminales aunque se estén ejecutando en ese momento.

## comandos at y cron

Para crear tareas con at podemos utilizar el propio comando que nos abrirá un prompt en el que ir ingresando las tareas
a ejecutar o hacer que lea la entrada estándar pasando los comandos mediante «tuberías», ya sabes el símbolo |

```bash
$ at 2:01 pm
warning: commands will be executed using /bin/sh
at Thu Aug 19 14:01:00 2021
at> touch archivo1.md
at> cp archivo1.md /home/victorhck/scripts
at> poweroff -h
at>
job 21 at Thu Aug 19 14:01:00 2021
```

La otra manera de crear una tarea es pasando el comando mediante la «tubería» con un comando, por ejemplo

```bash
echo "touch xxx.md" | at now +1 minute
```

### cron

Cron es un administrador de tareas de Linux que permite ejecutar comandos en un momento determinado, por ejemplo, cada
minuto, día, semana o mes. Si queremos trabajar con cron, podemos hacerlo a través del comando crontab.

Que es crontab ? Es un archivo de texto donde se listan todas las tareas que deben ejecutarse y el momento en el que
deben hacerlo.

Para poder abrir y crear un cron, tendríamos que ejecutar el siguiente comando:

```bash
crontab -e
```

La primera vez que abrimos este fichero, tendremos que seleccionar el editor que deseamos utilizar:

```bash
[username@hostname]:~$ crontab -e
no crontab for dominio-ejemplo - using an empty one
Select an editor.  To change later, run 'select-editor'.
  1. /bin/nano        <---- easiest
  2. /usr/bin/vim.basic
  3. /usr/bin/vim.tiny
Choose 1-3 [1]:
```

Una vez seleccionado el editor deseado, se nos abrirá el fichero para poder insertar el cron que deseamos programar.

Ejemplo:
Programamos un script que realiza una copia de seguridad todos los días a las 02:00 h de la mañana:

```bash
00 02 * * * /home/hosting/backup.sh
```

Ahora programamos el mismo script que realiza un backup, pero limitado al sábado y al domingo a las 03:00 de la mañana:

```bash
00 03 \* \* 6,7 /home/hosting/backup.sh
```

En este caso, ejecutamos el script cron.sh todos los miércoles a las 12:20 y guardar la salida en el fichero cron.log:

```bash
20 12 \* \* 3 /home/usuario/cron.sh >> /home/usuario/cron.log
```

Si queremos indicar dos o más valores en cada parámetro, es necesario separarlos por comas. Por ejemplo, para ejecutar
el script cron.sh todos los miércoles a las 12:10 h y a las 12:20 h:

```bash
10,20 12 \* \* 3 /home/usuario/cron.sh
```

Si queremos indicar que se ejecute el fin de semana cada 15 minutos podemos hacerlo de dos formas diferentes. Como hemos
hecho en el ejemplo anterior, con comas:

```bash
0,15,30,45 \* \* _ 6,7 /home/usuario/cron.sh
```

O bien usando la sintaxis \_/15:

```bash
_/15 _ \* \* 6,7 /home/usuario/cron.sh

```

Este es un ejemplo de ejecución de un fichero PHP cada 15 minutos:

```bash
_/15 _ \* \* \* /home/usuario/.bin/php /home/usuario/fichero.php
```

Si queremos que se ejecuten dos comandos, de forma consecutiva, separaremos los comandos con punto y coma:

```bash
_/15 _ \* \* 6,7 /home/usuario/cron.sh; /home/usuario/backup.sh
```

En el ejemplo que figura a continuación programamos la descarga de un fichero, todos los días, el día 8 de mayo a las
07:15 h:

```bash
15 7 8 5 \* wget -N http://dominio-ejemplo.com/documentacion.tar.gz
```

A continuación usaremos el mismo ejemplo, pero la descarga de un fichero solo se realizará el día 8 de mayo a las 07:15
h si ese día coincide que es lunes:

```bash
15 7 8 5 1 wget -N http://dominio-ejemplo.com/documentacion.tar.gz
```

Y ahora configuramos que la descarga del fichero el día 8 de mayo a las 07:15 h se realice solo si coincide de lunes a
viernes:

```bash
15 7 8 5 1-5 wget -N http://dominio-ejemplo.com/documentacion.tar.gz
``
```
