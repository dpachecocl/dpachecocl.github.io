---
theme: "just-the-docs"
title: "Instalación"
layout: default
nav_order: 1
parent: "Lab Ofensivo" 
---
# Descargas

## VMWare Workstation 17
* Se puede licenciar para uso personal.
* Es necesario registrarse en [Broadcom.com](https://www.broadcom.com/).
* Para este caso, descargamos la versión **VMware-workstation-full-17.5.2**.
* Descarga: [VMware Workstation ](https://blogs.vmware.com/workstation/2024/05/vmware-workstation-pro-now-available-free-for-personal-use.html)

## Ubuntu Desktop
* Usaremos esta distribución de Ubuntu para realizar pruebas ofensivas.
* Para este caso, descargamos la versión **24.04.1 LTS**.
* [Descargar Ubuntu Desktop](https://ubuntu.com/download/desktop)

## GNS3
* Es necesario registrarse en la página oficial.
* Para este caso, descargamos la versión **2.2.49**.
* [Descargar GNS3](https://www.gns3.com/software/download)

## GNS3 VM
* Es necesario registrarse en la página oficial.
* Para este caso, descargamos la versión para VMware Workstation (versión **2.2.49**).
* [Descargar GNS3 VM](https://www.gns3.com/software/download-vm)

# Instalación

## VMWare Workstation 17
* Instalamos el software con todas las opciones predeterminadas.
* En la opción de licencia, seleccionamos "Ingresar después".
* Al abrir VMware Workstation, seleccionamos la opción "Use VMware Workstation for Personal Use", luego continuamos y finalizamos.

## Ubuntu Desktop
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
* Una vez finalizada la instalacion, nos

## GNS3 VM
* Descomprimimos el archivo descargado.
* Ejecutamos el archivo **GNS3 VM.ova**.
* Al ser solicitado cómo abrir el archivo, seleccionamos **VMware Workstation**.
* Asignamos un nombre, el directorio para la nueva máquina virtual y seleccionamos **Importar**.
* Opcionalmente, podemos editar la máquina virtual para asignar más recursos.

## GNS3
* Ejecutamos el archivo **GNS3-2.2.49-all-in-one-regular.exe**.
* En la ventana de selección de componentes (**Choose Components**), dejamos las opciones por defecto seleccionadas (**GNS3 Desktop** y **Tools**) y seleccionamos **Siguiente**. Nota: Durante el proceso de instalación, es posible que algunas librerías ya estén instaladas, por lo que no será necesario reinstalarlas. Además, durante la instalación, se pedirá un correo para registrar algunas herramientas como Solar-Putty.
* Al finalizar la instalación, opcionalmente se ofrece un **Toolset de SolarWinds** para comprar. En mi caso, no lo uso, por lo que seleccioné **No** y continué con **Siguiente** para finalizar la instalación.
* Al abrir GNS3 por primera vez, aparecerá un **Setup Wizard**, donde debemos elegir la opción **Run appliances in a virtual machine**. Posteriormente, debemos asociarlo a VMware y a la máquina virtual creada en la sección anterior.
* Si este proceso se realizó correctamente, en el panel de GNS3 aparecerá la máquina virtual con un botón verde indicando que está activa.

# Configuración

## GNS3
* Una vez que GNS3 está en funcionamiento, es necesario agregar las imágenes de los dispositivos que se van a implementar. Estos pueden ser múltiples dispositivos, los cuales deben descargarse e incorporarse a GNS3. El listado de dispositivos compatibles se puede encontrar en [GNS3 Marketplace](https://www.gns3.com/marketplace/appliances). (Es importante tener en cuenta que algunas imágenes requieren cuentas de usuario o licenciamiento).
