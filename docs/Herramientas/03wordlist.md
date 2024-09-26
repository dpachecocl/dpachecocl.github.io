---
theme: "just-the-docs"
title: "Wordlist"
layout: default
nav_order: 3
parent: "Herramientas"
---
# **Wordlists (Diccionario)**
## Descarga de rockyou
```bash
nanomkdir /home/lesand/Desktop/tools/diccionarios
cd /home/lesand/Desktop/tools/diccionarios
wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz
tar -xzvf rockyou.txt.tar.gz && rm rockyou.txt.tar.gz
```
## Creacion de script en python para la generacion de diccionario
```bash
nano /home/lesand/Desktop/tools/diccionarios/wordlist.py
```
