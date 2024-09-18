---
theme: "just-the-docs"
title: "Instalación de herramientas."
layout: default
order: 4
---
# **Instalación**

## VMWare Workstation 17.
* Instalamos el software con todas las opciones predeterminadas.
* En la opción de licencia, seleccionamos "Ingresar después".
* Al abrir VMware Workstation, seleccionamos la opción "Use VMware Workstation for Personal Use", luego continuamos y finalizamos.
Nota: Durante la instalacion de la ultima version de VMWare es necesario ejecutar los siguientes comandos en la interfaz de comandos ejecutada en modo administrador
```
C:\WINDOWS\system32> net localgroup /add "Authenticated Users"
PS C:\WINDOWS\system32> net localgroup /add "Users"
PS C:\WINDOWS\system32> net localgroup /add "Administrators"
```


## Ubuntu Desktop.
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

# **Configuración.**

## GNS3
* Una vez que GNS3 está en funcionamiento, es necesario agregar las imágenes de los dispositivos que se van a implementar. Estos pueden ser múltiples dispositivos, los cuales deben descargarse e incorporarse a GNS3. El listado de dispositivos compatibles se puede encontrar en [GNS3 Marketplace](https://www.gns3.com/marketplace/appliances). (Es importante tener en cuenta que algunas imágenes requieren cuentas de usuario o licenciamiento).

# Instalación de MikroTik en GNS3

**1. Descarga de MikroTik**
- Visita el siguiente enlace para descargar la imagen: [MikroTik CHR](https://download.mikrotik.com/routeros/6.40.6/chr-6.40.6.img.zip).
**2. Descomprimir el archivo**
- Extrae el archivo ZIP descargado. Asegúrate de que el archivo `chr-6.40.6.img` esté disponible.
**3. Agregar un nuevo template en GNS3**
- Abre GNS3 y selecciona **New Template**.
**4. Seleccionar la opción de instalación**
- Elige la opción **Install an appliance from the GNS3 server (recommended)** y haz clic en **Next**.
**5. Buscar el appliance**
- En el campo de búsqueda (filter), escribe **chr** y selecciona **MikroTik CHR QEMU**. Luego haz clic en **Install**.
**6. Seleccionar la instalación en la GNS3 VM
- Asegúrate de que esté seleccionada la opción **Install the appliance on the GNS3 VM (recommended)** y haz clic en **Next**.
**7. Configurar QEMU**
- Mantén la opción por defecto seleccionada: `/bin/qemu-system-x86_64 (v4.2.1)` y haz clic en **Next**.
**8. Elegir la versión**
- Selecciona la versión más antigua de la lista (por ejemplo, 6.48.6) y selecciona **Create a new version**.
**9. Configurar la nueva versión**
- Asigna el nombre **6.40.6** y establece el nombre de archivo como **chr-6.40.6.img**.
**10. Importar la imagen**
- En la nueva versión creada, selecciona **chr-6.40.6.img** y haz clic en **Import**. Esto cargará la imagen en la máquina virtual, y el estado cambiará a **Ready to install**.
**11. Completar la instalación**
- Selecciona la nueva versión que has creado, haz clic en **Next** y acepta la instalación.
**12. Verificar el nuevo dispositivo**
- Una vez completada la instalación, revisa el nuevo dispositivo en GNS3 para asegurarte de que esté configurado correctamente.
