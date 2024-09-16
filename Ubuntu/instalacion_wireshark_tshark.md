---
theme: "just-the-docs"
title: "Instalación Wireshark & Tshark"
layout: default
nav_order: 2
parent: "Ubuntu" 
---
# Instalacion de Tshark y Wireshark
## Actualización
```
sudo apt-get update && sudo apt-get upgrade -y
```

## Instalacion de Tshark
```
sudo apt-get install tshark -y
```
## Configurar permisos para realizar capturas sin requerir permisos de superusuario

```
sudo usermod -aG wireshark lesand
```
```
sudo chgrp wireshark /usr/bin/dumpcap
```
```
sudo chmod 750 /usr/bin/dumpcap
```

```
sudo setcap cap_net_raw,cap_net_admin=eip /usr/bin/dumpcap
```
```
reboot
```
## Instalacion de Wireshark
```
sudo apt-get install wireshark -y
```

