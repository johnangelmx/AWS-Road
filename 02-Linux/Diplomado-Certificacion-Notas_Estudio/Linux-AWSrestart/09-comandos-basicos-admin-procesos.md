# Comandos basicos para la administracion de procesos

## El comando PS

El comando ps (estado del proceso) es un comando de sistema que muestra informacion sobre los procesos en ejecucion.

```bash
[username@hostname ~]$ ps
```

### Para que querria utilizar el comando?

Dado que linux es bueno para ejecutar varios procesos a la vez, como usuario, es posible que deba comprender que
procesos se ejecutan , cuanto tiempo lleva ejecutandose un proceso y bajo que PID (Process ID) se encuentra el
proceso.Esta infomacion puede ser util para solucionar problemas y ahorrar tiempo y esfuerzo.

```bash
[username@hostname ~]$ ps
```

Resultado:

```bash
  PID TTY          TIME CMD
    9 pts/0    00:00:01 zsh
  464 pts/0    00:00:00 ps
```

```bash
[username@hostname ~]$ ps -ef
```

Resultado:

```bash
UID        PID  PPID  C STIME TTY          TIME CMD
root         1     0  0 17:30 ?        00:00:00 /init
root         7     1  0 17:30 ?        00:00:00 /init
root         8     7  0 17:30 ?        00:00:00 /init
angel        9     8  3 17:30 pts/0    00:00:01 -zsh
angel      478     9  0 17:31 pts/0    00:00:00 ps -ef
```

## Comando pidof

El comando pidof devuelve el PID (Process ID) de un proceso especifico o de todos los procesos que coinciden con un
nombre de proceso.

```bash
[username@hostname ~]$ pidof zsh
```

Resutado

```bash
9
```

## Comando pstree

El comando pstree muestra el estado de los procesos en una estructura de arbol.

```bash
[username@hostname ~]$ pstree
```

Resultado:

```bash
init─┬─init───init───zsh───pstree
     └─2*[{init}]
```

## comando top

El comando top muestra un resumen del sistema en tiempo real e informacion de un sistema en ejecucion. Muestra
informacion y una lista de procesos o subprocesos que se estan administrando.

```bash
[username@hostname ~]$ top
```

Resultado

```bash
top - 17:46:04 up 15 min,  0 users,  load average: 0.00, 0.00, 0.00
Tasks:   5 total,   1 running,   4 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   7879.0 total,   7275.5 free,    251.6 used,    351.9 buff/cache
MiB Swap:   2048.0 total,   2048.0 free,      0.0 used.   7401.3 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    1 root      20   0    1744   1084   1016 S   0.0   0.0   0:00.01 init
    7 root      20   0    1752     72      0 S   0.0   0.0   0:00.00 init
    8 root      20   0    1752     80      0 S   0.0   0.0   0:00.03 init
    9 angel     20   0   13692   7852   4676 S   0.0   0.1   0:01.68 zsh
  578 angel     20   0   10872   3780   3268 R   0.0   0.0   0:00.03 top
```

En el cual podemos observar procesos y subprocesos, el tiempo que se esta ejecutando, el uso de CPU y MEMORIA, y el
comando que se esta ejecutando.

## comando kill

El comando kill es un comando de sistema que permite matar procesos.

```bash
[username@hostname ~]$ kill -9 <PID>
```

Dando como resultado en este caso el cierre del proceso zsh, que es el gestor de shell predeterminado en linux.

## comando nice y renice

El comando Nice iniciará un proceso con una prioridad de programación definida por el usuario. El comando Renice
modificará la prioridad de programación de un proceso en ejecución. El kernel de Linux programa el proceso y asigna el
tiempo de CPU en consecuencia para cada uno de ellos

El comando nice establece la prioridad de un proceso en el caso de la prioridad mas alta es -20 y la mas baja es de 19

```bash
[username@hostname ~]$ nice -n -20 zsh
```

Estableciendo asi la prioridad mas alta del proceso zsh.  
Y para ver el cambio con `pidof` podemos ver el cambio

```bash
[username@hostname ~]$ pidof zsh
642 9
```

Viendo asi el cambio de proceso y la importancia de la prioridad.

```bash
[username@hostname ~]$ renice -n 19 zsh
```
