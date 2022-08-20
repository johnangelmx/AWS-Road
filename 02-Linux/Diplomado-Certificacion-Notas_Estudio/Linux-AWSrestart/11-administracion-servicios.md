# Administracion de servicios en linux

- Explicacion de comandos comunes que se utilizan para administrar los servicios en linux
- Explicar los comando comunes que se utilizan para monitorear los servicios en linux

## Comando systemctl

Systemctl es una utilidad utilizada por systemd para administrar el sistema y el administrador de servicios. Muchas
distribuciones modernas de Linux como Ubuntu, Debian, Fedora, Linux Mint, OpenSuSE, Redhat han adoptado systemd como su
sistema de inicio predeterminado.

### Servicio de inicio / parada / reinicio / recarga de Systemctl

Como si fuera cualquier otro manejador de procesos tenemos los procesos basicos y con ello los sigueinte comandos

```bash
systemctl start <proceso>
```

```bash
systemctl stop <proceso>
```

```bash
systemctl restart <proceso>
```

```bash
systemctl reload <proceso>
```

### Systemctl comprobar el estado del servicio

```bash
systemctl status <proceso>
```

Es para comprobar el estado del servicio.

### Verifique y habilite / deshabilite el servicio en el arranque

```bash
systemctl enable <proceso>
```

```bash
systemctl disable <proceso>
```

Para verificar si un servicio está habilitado en el arranque o no, ejecute:

```bash
systemctl is-enable <proceso>
```
