---
theme: "just-the-docs"
title: "Ataque a Contraseñas"
layout: default
nav_order: 6
parent: "ARRAY DIINF 2024"
---
# Cifradas
## Cisco7
```bash
cd /home/lesand/Desktop/tools/ciscot7
python3 ciscot7.py -d -p '10420C0A041916595C5678'
```
# Hashes
## Hashcat
```bash
hashcat -m 500 -a 0 '$1$uumX$4iDPCazWt.4qdJ5VYlakF/' /home/lesand/Desktop/tools/diccionarios/diccionario.txt
```
