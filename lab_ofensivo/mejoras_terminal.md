---
theme: "just-the-docs"
title: "Mejoras de la Terminal"
layout: default
nav_order: 2
parent: "Lab Ofensivo" 
---
# Instalacion de Tshark y Wireshark
## Actualización

**Descripción**: Actualiza la lista de paquetes disponibles y sus versiones, luego instala las últimas versiones de todos los paquetes actualmente instalados en el sistema.
```
sudo apt-get update && sudo apt-get upgrade -y
```

## Instalacion de Tshark
**Descripción**: instala tshark en Ubuntu, solicita algunas confirmaciones adicionales
```
sudo apt-get install tshark -y
```
**Nota**: Antes de finalizar la instalación, se debe indicar si se dará permiso a los usuarios no privilegiados para capturar datos. Con esta configuración se puede ejecutar tshark pero no reconoce todas las interfaces si no se ejecuta con privilegios de superusuario (`sudo`). En este caso si daremos permiso.

## Configurar permisos para realizar capturas sin requerir permisos de superusuario
**Descripción:** Este comando añade al usuario `lesand` al grupo `wireshark`, permitiéndole acceder a los recursos y permisos asociados a ese grupo.
```
sudo usermod -aG wireshark lesand
```
**Donde**:
- `sudo`: Ejecuta el comando con privilegios de superusuario.
- `usermod`: Es una herramienta para modificar las cuentas de usuario.
- `-aG`: Añade el usuario a un grupo sin eliminarlo de otros grupos. `-a` significa "append" (agregar) y `G` indica que se añade a un grupo.
- `wireshark`: Es el nombre del grupo al que se añadirá el usuario.
- `lesand`: Es el nombre del usuario que se añadirá al grupo `wireshark`.

**Descripción:** Este comando cambia el grupo propietario del archivo `/usr/bin/dumpcap` al grupo `wireshark`.
```
sudo chgrp wireshark /usr/bin/dumpcap
```
**Donde**:
- `sudo`: Ejecuta el comando con privilegios de superusuario.
- `chgrp`: Cambia el grupo propietario de un archivo o directorio.
- `wireshark`: Es el nuevo grupo propietario.
- `/usr/bin/dumpcap`: Es el archivo al que se le cambiará el grupo propietario.

**Descripción:** Este comando establece los permisos del archivo `/usr/bin/dumpcap` a 750, otorgando permisos de lectura, escritura y ejecución al propietario, permisos de lectura y ejecución al grupo, y ningún permiso a otros usuarios.
```
sudo chmod 750 /usr/bin/dumpcap
```
**Donde**:
- `sudo`: Ejecuta el comando con privilegios de superusuario.
- `chmod`: Cambia los permisos de acceso de un archivo o directorio.
- `750`: Especifica los nuevos permisos del archivo. En este caso, el propietario tendrá permisos de lectura, escritura y ejecución (7), el grupo tendrá permisos de lectura y ejecución (5), y otros no tendrán ningún permiso (0).
- `/usr/bin/dumpcap`: Es el archivo cuyos permisos se cambiarán.

**Descripción:** Este comando otorga al archivo `/usr/bin/dumpcap` las capacidades `cap_net_raw` y `cap_net_admin`, permitiendo que este archivo realice operaciones de red sin necesidad de privilegios de superusuario.
```
sudo setcap cap_net_raw,cap_net_admin=eip /usr/bin/dumpcap
```
**Donde**:
- `sudo`: Ejecuta el comando con privilegios de superusuario.
- `setcap`: Establece capacidades en archivos ejecutables.
- `cap_net_raw,cap_net_admin=eip`: Especifica las capacidades a establecer. `cap_net_raw` permite el uso de paquetes sin procesar (raw packets) y `cap_net_admin` permite varias operaciones administrativas de red. `eip` significa que estas capacidades se aplican al archivo cuando se ejecuta (effective, inherited, permitted).
- `/usr/bin/dumpcap`: Es el archivo al que se le establecerán las capacidades.

**Descripción:** Este comando reinicia el sistema operativo par que se apliquen los cambios anterires.
```
reboot
```
## Instalacion de Wireshark
**Descripción**: instala Wireshark en Ubuntu.
```
sudo apt-get install wireshark -y
```

