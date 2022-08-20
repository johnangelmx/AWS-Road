# Otros comandos básicos

Hasta ahora hemos visto ciertos comando útiles del dia a dia , pero falta otros comando.

## Comando echo

El comando echo nos permite mostrar un texto en la terminal.

```bash
username@hostname:~$ echo "Hola mundo"
Hola mundo
```

## Comando cat

El comando cat nos permite mostrar un fichero en la terminal.

```bash
username@hostname:~$ cat prueba.txt
Hola mundo
```

Pero cabe resalta que su uso real es para concatenar varios ficheros.

```bash
username@hostname:~$ cat hola.txt mundo.txt
Hola
Mundo
```

---

## Mover ficheros

Hasta este punto hemos visto la creación y eliminación de ficheros , pero aun falta el moverlos y copiarlos...

## Comando mv

El comando mv nos permite mover un fichero o directorio.

```bash
username@hostname:~$ mv prueba.txt Test/
```

La sintaxis básica de mover un fichero , o en este caso el comando mv , es teniendo 2 parámetros , el primero seria el
fichero que queremos mover ya sea estando con la ruta relativa o con la absoluta , y el segundo seria la ruta donde
queremos moverlo.

### Cambiar nombre con el comando mv

Dentro de la sintaxis de mover un fichero , podemos cambiar el nombre del fichero que queremos mover, esto simplemente
seleccionando el primer parámetro el archivo a cambiar de nombre y el segundo parámetro el nuevo nombre del archivo.

```bash
username@hostname:~$ mv prueba.txt pruebaNuevoNombre.txt
```

Ruta absoluta:

```bash
username@hostname:~$ mv Test/prueba.txt Test/pruebaNuevoNombre.txt
```

---

## Comando cp

El comando cp nos permite copiar un fichero o directorio.

```bash
username@hostname:~$ cp prueba.txt Test/
```

La sintaxis básica de copiar un fichero , o en este caso el comando cp , es teniendo 2 parámetros , el primero seria el
fichero que queremos copiar ya sea estando con la ruta relativa o con la absoluta , y el segundo seria la ruta donde
queremos copiarlo.
