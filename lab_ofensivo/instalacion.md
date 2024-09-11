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
* [VMware Workstation Pro disponible gratuitamente para uso personal](https://blogs.vmware.com/workstation/2024/05/vmware-workstation-pro-now-available-free-for-personal-use.html)

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
* Ejecutamos el archivo GNS3-2.2.49-all-in-one-regular.exe
* En la ventana de seleccion de componentes (Choose Components) dejamos las opciones por defecto seleccionadas (GNS3 Desktop y Tools) y seleccionamos siguiente. Nota: Em el poroceso de instalacion puede que alguna libreria ya la tengamos instalada, por lo que no sera necesario reinstalarlas, ademas en el proceso de instalacion pedira un correo para registar algunas herramientas como solar putty.
* Al finalizar la instalacion opcionalmente ofrece un Toolset de solarwinds que se puede comprar que en mi caso no lo uso opcion no (seleccionar No) y siguiente para finalizar la instalacion.
* Luego al abrir GNS por primera vez aparecera un "Setup Wizard" donde debo elegir la opcion "Run appliances in a virtual machine" el cual debo asociar posteriormente a VMware y la maquina virtual creada en la seccion anterior.
* Si este proceso esta correctamente realizado en el panel de GNS3 aparecera esta maquina virtual con un boton verde.
