# El flujo de trabajo

## Inicio de sesion

Todas las sesiones de Linux comienzan con el proceso de inicio de sesión (proceso de autenticación predeterminado). Las
sesiones de Linux comienzan cuando el usuario introduce su nombre de usuario en la solicitud. El mensaje de inicio de
sesión se utiliza para autenticarse (probar la identidad del usuario) antes de utilizar un sistema Linux. Cuando se
escribe la contraseña, no aparece eco (no se muestra una línea de texto).

    login:

Nombre de usuario

    password:

Contrseña de usuario

El nombre de usuario se compara con el archivo/etc/.psswd, que se almacena en el directorio /etc

1. Nombre de usuario o nombre de inicio de sesión
2. Contraseña cifrada
3. ID de usuario
4. ID de grupo
5. Descripción del usuario
6. Directorio de inicio del usuario
7. shell de inicio de sesión del usuario

Durante el flujo de trabajo de inicio de sesión, el nombre se compara con el archivo /etc/passwd y la contraseña se
compara con el archivo /etc/shadow.

El perfil del usuario se carga desde los archivos almacenados en el directorio principal del usuario:

- /home/username/.bashrc
- /home/username/.bash_history
- /home/username/.bash_profile
