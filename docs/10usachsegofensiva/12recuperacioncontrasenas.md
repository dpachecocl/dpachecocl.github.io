---
theme: "just-the-docs"
title: "Recuperación de contraseñas"
layout: default
nav_order: 12
parent: "Seguridad Ofensiva"
---
# Recuperacion de contrasenas Cisco de tipo 7
## Cisco7
```bash
cd /home/lesand/Desktop/tools/ciscot7
python3 ciscot7.py -d -p '10420C0A041916595C5678'
```
# Recuperacion de contrasenas Cisco de tipo 5
## Hashcat
```bash
hashcat -m 500 -a 0 '$1$uumX$4iDPCazWt.4qdJ5VYlakF/' /home/lesand/Desktop/tools/diccionarios/diccionario.txt
```
# Recuperacion de contrasenas Cisco de tipo 8
# Recuperacion de contrasenas Cisco de tipo 9
