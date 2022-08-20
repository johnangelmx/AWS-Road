# Primeros Pasos

Ya tomamos un poco de teoría, ahora bien , si esta aquí en este punto te habrás dado cuenta que en entorno gráfico
podremos ver y manipular con el mouse, con simples clicks , pero en una terminal tendremos que escribir comandos para
hacer lo mismo que hacemos en un entorno gráfico, esa es la única diferencia dado que podremos hacer lo mismo que
hacemos con unos clicks con comandos que nosotros escribimos.

---

El primer contacto que tendremos sera el siguiente:

```bash
username@hostname:~$
```

El cual podremos ver que el username es el nombre de usuario que tenemos en el sistema y el hostname es el nombre de
nuestro equipo.

Esto lo veremos a diario por lo que tendremos que familiarizarnos con ello.

En mi caso es el siguiente:

```bash
angel@Lenovo:~$
```

Esto por que mis configuraciones fueron seleccionadas asi en la instalación de Ubuntu.

```bash
ec2@108.091.021.1:~$
```

Por otra situación podremos encontrarnos con terminales asi, siendo terminales remotas para uso de servidores, pero como
se menciono en la introducción esta vez sera una terminal local y para el uso de servidores la documentación esta en
esta misma plataforma.

---

## Comando pwd

El comando pwd nos permite ver la ruta actual en el sistema. Las siglas pwd significan "print working directory".

```bash
username@hostname:~$ pwd
/home/username
```

Este comando es imprescindible dado que nos permite saber donde estamos en el sistema, y su uso es casi
imprescindible.en el dia a dia en la manipulación de la terminal

## Comando ls

El comando ls nos permite ver los archivos que hay en el directorio actual, ls son las siglas de list(listar)

```bash
username@hostname:~$  ls
Descargas   Escritorio  Música   Publico
Documentos  Imágenes    Videos   Plantillas
```

## Comando cd

El comando cd nos permite cambiar de directorio. Las siglas cd significan "change directory". Cabe resaltar que a lo que
llamamos directorio, es mejor conocido como carpeta.

```bash
username@hostname:~$ cd Escritorio/
/home/username/Escritorio
```

## Comando mkdir

El comando mkdir nos permite crear un directorio. Las siglas mkdir significan "make directory".

```bash
username@hostname:~$ mkdir test
```

```bash
username@hostname:~$  ls
Descargas   Escritorio  Música   Publico
Documentos  Imágenes    Videos   Plantillas test
```

Prácticamente podemos crear cualquier tipo de directorio, como por ejemplo un directorio de imágenes, videos, etc.

## Comando rmdir

El comando rmdir nos permite eliminar un directorio. Las siglas rmdir significan "remove directory". Pero cabe resaltar
que no podemos eliminar un directorio que contenga archivos, tendrá que estar vació para remover directorios con
archivos lo veremos mas adelante

```bash
username@hostname:~$ rmdir test
```

```bash
username@hostname:~$  ls
Descargas   Escritorio  Música   Publico
Documentos  Imágenes    Videos   Plantillas
```

**Hasta este punto hemos visto como crear directorios, eliminar directorios, cambiar de directorios, y ver la ruta
actual.**
