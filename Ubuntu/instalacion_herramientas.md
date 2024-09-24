---
theme: "just-the-docs"
title: "Instalacion de Herramientas"
layout: default
nav_order: 5
parent: "Ubuntu" 
---

## Instalación de herramientas usando  `apt-get install`
```bash
sudo apt-get install nmap -y
sudo apt-get install openssh-server -y
sudo apt-get install hping3 -y
sudo apt-get install hashcat -y
sudo apt-get install python3-scapy -y
sudo apt-get install cewl -y
sudo apt-get install crunch -y
sudo apt-get install onesixtyone -y
sudo apt-get install hydra-gtk -y
sudo apt-get install tcpreplay -y
```
## Instalación de herramientas usando archivos `.sh`
### BurpSuite
Descargar Burp Suite Community Edition desde: [https://portswigger.net/burp/releases](https://portswigger.net/burp/releases), en este caso se ha descargado el siguiente archivo `burpsuite_community_linux_v2024_8_1.sh`.

```bash
cd ~/Downloads
chmod +x burpsuite_community_linux_v2024_8_1.sh
./burpsuite_community_linux_v2024_8_1.sh
```
Luego instalar con todas las opciones por defecto de forma grafica.

## Instalación de herramientas usando archivos `git clone`
```bash
cd /home/lesand/Desktop/tools
git clone https://github.com/theevilbit/ciscot7.git
git clone https://github.com/Mebus/cupp.git
```
