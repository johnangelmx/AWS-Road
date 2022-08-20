# Superuser Root en linux

En linux se tiene la peculiaridad que si iniciamos una maquina y en esta , creamos un único usuario para un único uso ,
este usuario no tiene control total de la maquina, es decir, en ese momento tenemos un usuario normal y un super usuario
root.

Pero , porque pasa esto? .A diferencia de windows que el único usuario tiene permisos de administrador , en linux el
super usuario root tiene permisos de administrador y el usuario normal no tiene ningún permiso de administrador.

Cabe resaltar que depende mucho la distribución para poder instalar paquetes de software, en ubuntu podemos instalar sin
problema paquetes de software de forma sencilla , pero en Debian no es asi, tenemos que instalar paquetes con el permiso
de super usuario root. Pero esto no tiene que preocuparnos porque tenemos 2 casos de ayuda , el primero es que
dependiendo el sistema operativo no avisara de algún problema , y el segundo es la herramienta `sudo`.

La herramienta sudo nos permite ejecutar comandos de forma sencilla y con permisos de super usuario root.

```bash
# Instalar paquetes de software con permisos de super usuario root
[username@hostname:~]$ sudo apt-get install software
```

Pero si queremos usar permisos de administrador, tenemos que cambiar de usuario. y ejecutar el comando `sudo su`

```bash
# Cambiar de usuario
[username@hostname:~]$ sudo su
```

El comando su nos permite cambiar de usuario , pero al haber unicamente un usuario en el sistema , no hace falta que le
indiquemos a la maquina que a que usuario cambiaremos, porque por defecto el usuario que ejecuta el comando su es el
usuario root.
