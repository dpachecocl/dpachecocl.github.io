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
