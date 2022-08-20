# Uso de opciones en los comandos

Hasta ahora sabemos borrar un directorio o archivo vació

Es momento de saber que lo comandos también se les pueden pasar opciones.

---

## Opciones en el comando rm

`- r` y `--recursive` : Elimina recursivamente todos los archivos y directorios que se encuentren dentro del directorio
actual.

```bash
username@hostname:~$ rm -r test
```

`-r -i` y `--recursive --interactive` : Elimina recursivamente todos los archivos y directorios que se encuentren dentro
del directorio actual, pero pregunta antes de eliminar cada archivo o directorio.

```bash
username@hostname:~$ rm -r -i test
```

O también puedes utilizar:

```bash
username@hostname:~$ rm -ri test
```

---

## man & help

Teniendo en cuenta el aspecto anterior hemos denotado que podemos tener muchas opciones para diferentes comandos, para
no hacerlo largo alguna explicación de un comando determinado , señalaremos conforme avancemos en la documentación.

Pero linux ofrece por defecto predeterminado dos tipos de ayuda en cuanto a comandos:

`man <comando>`:

```bash
username@hostname:~$man rm

SYNOPSIS
       rm [OPTION]... [FILE]...

DESCRIPTION
       This  manual  page  documents the GNU version of rm.  rm removes each specified file.  By default, it does not
       remove directories.

       If the -I or --interactive=once option is given, and there are more than three files or the -r, -R,  or  --re‐
       cursive are given, then rm prompts the user for whether to proceed with the entire operation.  If the response
       is not affirmative, the entire command is aborted.

       Otherwise, if a file is unwritable, standard input is a terminal, and the -f or --force option is  not  given,
       or the -i or --interactive=always option is given, rm prompts the user for whether to remove the file.  If the
       response is not affirmative, the file is skipped.

OPTIONS
       Remove (unlink) the FILE(s).

       -f, --force
              ignore nonexistent files and arguments, never prompt

       -i     prompt before every removal

       -I     prompt once before removing more than three files, or when removing recursively;  less  intrusive  than
              -i, while still giving protection against most mistakes

       --interactive[=WHEN]
              prompt according to WHEN: never, once (-I), or always (-i); without WHEN, prompt always
...
```

Y el comando help  
`rm --help`

```bash
Usage: rm [OPTION]... [FILE]...
Remove (unlink) the FILE(s).

  -f, --force           ignore nonexistent files and arguments, never prompt
  -i                    prompt before every removal
  -I                    prompt once before removing more than three files, or
                          when removing recursively; less intrusive than -i,
                          while still giving protection against most mistakes
      --interactive[=WHEN]  prompt according to WHEN: never, once (-I), or
                          always (-i); without WHEN, prompt always
      --one-file-system  when removing a hierarchy recursively, skip any
                          directory that is on a file system different from
                          that of the corresponding command line argument
      --no-preserve-root  do not treat '/' specially
      --preserve-root[=all]  do not remove '/' (default);
                              with 'all', reject any command line argument
                              on a separate device from its parent
  -r, -R, --recursive   remove directories and their contents recursively
  -d, --dir             remove empty directories
  -v, --verbose         explain what is being done
      --help     display this help and exit
      --version  output version information and exit

By default, rm does not remove directories.  Use the --recursive (-r or -R)
option to remove each listed directory, too, along with all of its contents.

To remove a file whose name starts with a '-', for example '-foo',
use one of these commands:
  rm -- -foo

  rm ./-foo

Note that if you use rm to remove a file, it might be possible to recover
some of its contents, given sufficient expertise and/or time.  For greater
assurance that the contents are truly unrecoverable, consider using shred.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Report rm translation bugs to <https://translationproject.org/team/>
Full documentation at: <https://www.gnu.org/software/coreutils/rm>
or available locally via: info '(coreutils) rm invocation'
```

**Asi demostrando que todo el tiempo existe soporte a la hora de usar linux**.
