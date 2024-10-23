---
theme: "just-the-docs"
title: "Instalacion de Herramientas"
layout: default
nav_order: 3
parent: "ARRAY DIINF 2024"
---
# Instalacion de Tshark y Wireshark
## Actualización
```bash
sudo apt-get update && sudo apt-get upgrade -y
```

## Instalacion de Tshark
```bash
sudo apt-get install tshark -y
```

## Configurar permisos para realizar capturas sin requerir permisos de superusuario
```bash
sudo usermod -aG wireshark lesand
sudo chgrp wireshark /usr/bin/dumpcap
sudo chmod 750 /usr/bin/dumpcap
sudo setcap cap_net_raw,cap_net_admin=eip /usr/bin/dumpcap
```
```bash
reboot
```

## Instalacion de Wireshark
```bash
sudo apt-get install wireshark -y
```
# Instalacion de Otras Herramientas usando  `apt-get install`
```bash
sudo apt-get install nmap -y
sudo apt-get install hashcat -y
sudo apt-get install python3-scapy -y
sudo apt-get install cewl -y
sudo apt-get install crunch -y
sudo apt-get install hydra-gtk -y
```
## Instalación de herramientas usando archivos `git clone`
```bash
mkdir /home/lesand/Desktop/tools
cd /home/lesand/Desktop/tools
git clone https://github.com/theevilbit/ciscot7.git
git clone https://github.com/Mebus/cupp.git
```
