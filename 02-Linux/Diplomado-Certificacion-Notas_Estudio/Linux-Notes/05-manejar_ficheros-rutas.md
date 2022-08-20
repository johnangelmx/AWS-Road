# Manejar ficheros y rutas

La manipulación de ficheros o como habitualmente decimos archivos es de suma importancia dia con dia en la vida de una
persona, por ello es que es importante que se entienda bien como funciona la manipulación de ficheros y como se usa la
terminal de linux.

---

## Comando touch

El comando touch nos permite crear un fichero.

```bash
username@hostname:~$ touch test.txt
```

---

### Ejemplo practico

```bash
username@hostname:~$ pwd
/home/username
```

```bash
username@hostname:~$ ls
Test
```

```bash
username@hostname:~$ cd Test
```

Y dentro del directorio Test, haremos el ejemplo de touch:

```bash
username@hostname:~/Test$ touch test.txt
```

```bash
username@hostname:~/Test$ ls
test.txt
```

En este punto ya podemos ver que hemos creado un fichero llamado test.txt dentro del directorio Test.
Pero ¿Como lo podemos remover? Bien asi como exited el comando `rmdir` para remover un directorio también existe:

## Comando rm

El comando rm nos permite eliminar un fichero.

```bash
username@hostname:~/Test$ rm test.txt
```

```bash
username@hostname:~/Test$ ls

```

## Tipos de rutas

Hasta el momento como te habrás dado cuenta , hemos navegado hasta la ubicación del lugar para realizar una tarea
especifica , ya se crear, eliminar o cambiar de directorio, pero dentro de una terminal existe formas en la cuales
podemos navegar por el sistema de archivos sin la necesidad de cambiar de directorio en donde estemos actualmente.

A esto se le llama rutas. Existen dos tipos de rutas:

- Ruta relativa
- Ruta absoluta

---

### Ruta relativa

La ruta relativa es prácticamente lo que hemos hecho hasta ahora , navegar dentro del sistema de archivos cambiando de
directorio y llenado a la ubicación del lugar donde queremos realizar una tarea especifica.

### Ruta absoluta

La ruta absoluta es una manera de navegar en el sistema de archivos sin la necesidad de cambiar de directorio, es decir
, nosotros podemos estar el el home del usuario y navegar hasta la ubicación del lugar donde queremos realizar una tarea
especifica simplemente escribiendo la ruta completa.

---

### Ejemplo de ruta absoluta

Planteemos el siguiente panorama , queremos crear un archivo en una carpeta ya creada con el nombre test , y el archivo
tendrá por nombre testAbsoluta.txt, pero nosotros no nos moveremos de la ruta principal que como hemos visto hasta ahora
es `/home/username` , por lo que la ruta absoluta sera `/home/username/test/testAbsoluta.txt`

```bash
username@hostname:~$ pwd
/home/username
```

```bash
username@hostname:~$ ls
test
```

Crearemos el archivo en la carpeta test:

```bash
username@hostname:~$ touch /home/username/test/testAbsoluta.txt
```

Y de la misma forma que podemos crear un fichero absoluto , podemos consultar el contenido del archivo de forma
absoluta.

```bash
username@hostname:~$ ls /home/username/test
testAbsoluta.txt
```

Demostrando asi la versatilidad de la terminal de linux.

---
