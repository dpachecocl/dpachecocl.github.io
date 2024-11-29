---
theme: "just-the-docs"
title: "Instalacion de herramientas"
layout: default
nav_order: 4
---
# **Instalación VMWare Workstation 17.**
* Instalamos el software con todas las opciones predeterminadas.
* En la opción de licencia, seleccionamos "Ingresar después".
* Al abrir VMware Workstation, seleccionamos la opción "Use VMware Workstation for Personal Use", luego continuamos y finalizamos.
Nota: Durante la instalacion de la ultima version de VMWare es necesario ejecutar los siguientes comandos en la interfaz de comandos ejecutada en modo administrador
```
C:\WINDOWS\system32> net localgroup /add "Authenticated Users"
PS C:\WINDOWS\system32> net localgroup /add "Users"
PS C:\WINDOWS\system32> net localgroup /add "Administrators"
```

# **Ubuntu Desktop.**
* Una vez iniciado VMware, seleccionamos la opción de crear una nueva máquina virtual.
* Elegimos la opción **Typical (recommended)**.
* Seleccionamos la opción **I will install the operating system later**.
* Elegimos **Linux - Ubuntu 64-bit**.
* Indicamos el nombre de la máquina virtual y la ubicación.
* Seleccionamos el tamaño del disco (200 GB en este caso) y marcamos la opción **Store virtual disk as a single file**.
* Finalizamos.
* Luego, editamos la máquina virtual y en la opción de **CD/DVD** asociamos la imagen ISO descargada de Ubuntu.
* En la opción **Display**, desactivamos la opción **Accelerate 3D graphics** y aceptamos los cambios.
* Iniciamos la máquina virtual.
* Seleccionamos la opción **Try or Install Ubuntu**.
* Durante la instalación, elegimos el idioma, opciones de accesibilidad, tipo de teclado, etc.
* Creamos una cuenta, indicamos el nombre de la máquina y una contraseña, seleccionamos la zona horaria e iniciamos la instalación.
* Una vez finalizada la instalación, reiniciamos.

# **GNS3 VM**

## GNS3 VM.
* Descomprimimos el archivo descargado.
* Ejecutamos el archivo **GNS3 VM.ova**.
* Al ser solicitado cómo abrir el archivo, seleccionamos **VMware Workstation**.
* Asignamos un nombre, el directorio para la nueva máquina virtual y seleccionamos **Importar**.
* Opcionalmente, podemos editar la máquina virtual para asignar más recursos.

## GNS3.
* Ejecutamos el archivo **GNS3-2.2.49-all-in-one-regular.exe**.
* En la ventana de selección de componentes (**Choose Components**), dejamos las opciones por defecto seleccionadas (**GNS3 Desktop** y **Tools**) y seleccionamos **Siguiente**. Nota: Durante el proceso de instalación, es posible que algunas librerías ya estén instaladas, por lo que no será necesario reinstalarlas. Además, durante la instalación, se pedirá un correo para registrar algunas herramientas como Solar-Putty.
* Al finalizar la instalación, opcionalmente se ofrece un **Toolset de SolarWinds** para comprar. En mi caso, no lo uso, por lo que seleccioné **No** y continué con **Siguiente** para finalizar la instalación.
* Al abrir GNS3 por primera vez, aparecerá un **Setup Wizard**, donde debemos elegir la opción **Run appliances in a virtual machine**. Posteriormente, debemos asociarlo a VMware y a la máquina virtual creada en la sección anterior.
* Si este proceso se realizó correctamente, en el panel de GNS3 aparecerá la máquina virtual con un botón verde indicando que está activa.

### En relación a GNS3
* Una vez que GNS3 está en funcionamiento, es necesario agregar las imágenes de los dispositivos que se van a implementar. Estos pueden ser múltiples dispositivos, los cuales deben descargarse e incorporarse a GNS3. El listado de dispositivos compatibles se puede encontrar en [GNS3 Marketplace](https://www.gns3.com/marketplace/appliances). (Es importante tener en cuenta que algunas imágenes requieren cuentas de usuario o licenciamiento).

# **Mikrotik**
## Ejemplo de virtualización de Mikrotik en GNS3

1. **Descarga de MikroTik**: [Descargar MikroTik CHR](https://download.mikrotik.com/routeros/6.40.6/chr-6.40.6.img.zip) (imagen img)
2. **Descomprimir el archivo**.
3. En GNS3, seleccionar **New Template**.
4. Seleccionar la opción **Install an appliance from the GNS3 server (recommended)** y hacer clic en **Next**.
5. En el filtro, buscar **chr**, seleccionar **MikroTik CHR QEMU** y hacer clic en **Install**.
6. Asegurarse de que esté seleccionada la opción **Install the appliance on the GNS3 VM (recommended)** y hacer clic en **Next**.
7. Dejar la opción de QEMU por defecto seleccionada (`/bin/qemu-system-x86_64 (v4.2.1)`) y hacer clic en **Next**.
8. Seleccionar la versión más antigua de la lista (6.48.6) y elegir **Create a new version**.
9. Asignar como nombre **6.40.6** y como nombre de archivo **chr-6.40.6.img**.
10. En la nueva versión creada, seleccionar **chr-6.40.6.img** y hacer clic en **Import** (esto cargará la imagen en la máquina virtual) y el estado cambiará a **Ready to install**.
11. Seleccionar la nueva versión, hacer clic en **Next** y aceptar la instalación.
12. Revisar el nuevo dispositivo.

## Ejemplo de virtualización de Mikrotik en VMware
**Descarga de MikroTik**: [Descargar MikroTik CHR](https://download.mikrotik.com/routeros/6.40.6/chr-6.40.6.vmdk) (imagen VMDK).

1. Crear una nueva máquina virtual. En la página inicial, al crear la nueva máquina virtual, seleccionar la opción **Typical (recommended)** y hacer clic en **Next**.
2. Luego, seleccionar la opción **I will install the operating system later** y hacer clic en **Next**.
3. A continuación, elegir **Linux 6.x kernel 64 bits** como sistema operativo y hacer clic en **Next**.
4. Asignar un nombre a la máquina virtual y hacer clic en **Next**.
5. Posteriormente, seleccionar **Store virtual disk as a single file** (el tamaño da lo mismo porque se reemplazará el disco después) y hacer clic en **Next**.
6. Finalizar la instalación.
7. Ahora tenemos dos opciones:
   1. Reemplazar el disco de la máquina copiando el archivo descargado en la carpeta de instalación de la máquina virtual y renombrarlo con el mismo nombre.
   2. La otra opción es editar la máquina virtual, eliminar el disco (con la opción **Remove**) y luego agregar el disco descargado con la opción **Add**.
