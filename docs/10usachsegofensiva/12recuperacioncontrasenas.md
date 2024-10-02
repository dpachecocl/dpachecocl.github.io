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
```bash
hashcat -m 9200 -a 0 '$8$I2yTFYHY9vJDaM$ZqDV0iy5F/qCdV4QkwVCqbRgd6q8uTzmAoHfOBC2Zgk' /home/lesand/Desktop/tools/diccionarios/diccionario.txt
```
# Recuperacion de contrasenas Cisco de tipo 9
```bash
hashcat -m 9300 -a 3 '$9$XdLjmPYCuppgvM$Js4qrU4S9d.8dsTozShD24X3oZRj4Er/0AZPIspHp9I' 'lesand?d?d?d?d'
```
