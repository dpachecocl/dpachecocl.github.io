---
theme: "just-the-docs"
title: "Reconocimiento"
layout: default
nav_order: 5
parent: "ARRAY DIINF 2024"
---
# GHDB
intext:"WebFig Login" & intitle:"RouterOS router configuration page"
# Shodan
mikrotik os:"MikroTik RouterOS 6.22"
# NMAP
# Ejemplos Nmap
- `nmap -p 22 localhost`  
  Este comando escanea el puerto 22 (comúnmente utilizado para **SSH**) en la máquina local (**localhost**), buscando servicios que estén escuchando en ese puerto.

- `nmap 192.168.85.134`  
  Este comando realiza un escaneo *TCP Connect Scan* a la dirección IP **192.168.85.134**, para detectar servicios escuchando en los puertos abiertos.

- `nmap -sT 192.168.85.134`  
  Este comando realiza un escaneo *TCP Connect Scan* a la dirección IP **192.168.85.134**, para detectar servicios escuchando en los puertos abiertos.

- `sudo nmap -sS 192.168.85.134`
  Este comando ejecuta un escaneo SYN scan (stealth scan) a la dirección IP **192.168.85.134**, con el objetivo de detectar puertos abiertos sin establecer conexiones TCP completas.
  
- `sudo nmap -p 22 192.168.85.134`  
  Este comando escanea específicamente el puerto 22.

- `sudo nmap -p 21-23,80 192.168.85.134`  
  Este comando escanea los puertos **21 a 23** (FTP, SSH, Telnet) y el puerto **80** (HTTP) en la dirección IP **192.168.85.134**.

- `sudo nmap -sS -p- 192.168.85.134`  
  Este comando realiza un escaneo SYN scan en **todos los puertos posibles** (de 0 a 65535) en la dirección IP **192.168.85.134**, buscando cualquier puerto abierto.

- `sudo nmap -sS -p 21 -O 192.168.85.134`  
  Este comando escanea el puerto **21** (FTP) utilizando un escaneo SYN scan a la dirección IP **192.168.85.134**, e intenta detectar el sistema operativo del objetivo con la opción `-O`.

- `sudo nmap -sS -p- -sV 192.168.85.134`  
  Este comando realiza un escaneo SYN scan en **todos los puertos posibles** de la dirección IP **192.168.85.134** y utiliza la opción `-sV` para obtener información detallada sobre las versiones de los servicios.

- `sudo nmap -sU 192.168.85.134`
  Este comando realiza un escaneo UDP.
