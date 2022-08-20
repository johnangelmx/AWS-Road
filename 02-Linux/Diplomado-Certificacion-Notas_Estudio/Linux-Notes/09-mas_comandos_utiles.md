# Mas Comandos útiles

## Comando grep

El comando grep busca una cadena de texto en un archivo.

```bash
username@hostname:~$ touch fichero.txt
```

ingresamos en el fichero el texto: ratones 15

```bash
username@hostname:~$ grep ratones fichero.txt
ratones 15
```

ingresamos en el fichero el texto: ratones 10

```bash
username@hostname:~$ grep ratones fichero.txt
ratones 15
ratones 10
```

---

## Opciones con el comando grep

`-n` y `--line-number` : Muestra el número de línea en la que se encuentra la cadena de texto.

```bash
username@hostname:~$ grep -n ratones fichero.txt
1: ratones 15
2: ratones 10
```

`-i` y `--ignore-case` : Ignora las mayúsculas y minúsculas.

```bash
username@hostname:~$ grep -i ratones fichero.txt
ratones 15
ratones 10
```

`-v` y `--invert-match` : Muestra todas las líneas que no contengan la cadena de texto.

```bash
username@hostname:~$ grep -v ratones fichero.txt
15
10
```

`-c` y `--count` : Muestra el número de líneas que contienen la cadena de texto.

```bash
username@hostname:~$ grep -c ratones fichero.txt
2
```

`-w` y `--word-regexp` : Busca la cadena de texto como una palabra completa.

```bash
username@hostname:~$ grep -w ratones fichero.txt
ratones 15
ratones 10
```
