---
theme: "just-the-docs"
title: "NMAP"
layout: default
nav_order: 2
parent: "Herramientas"
---
# NMAP
# Ejemplos Nmap
- `nmap -p 22 localhost`  
  Este comando escanea el puerto 22 (comúnmente utilizado para **SSH**) en la máquina local (**localhost**), buscando servicios que estén escuchando en ese puerto.

- `nmap 192.168.85.134`  
  Este comando realiza un escaneo básico en la dirección IP **192.168.85.134**, buscando puertos abiertos y servicios disponibles.

- `nmap -sT 192.168.85.134`  
  Este comando realiza un escaneo completo de conexiones TCP (*TCP Connect Scan*) en la dirección IP **192.168.85.134**, para detectar servicios escuchando en los puertos abiertos.

- `sudo nmap -sS 192.168.85.134`  
  Este comando ejecuta un escaneo SYN sigiloso en la dirección IP **192.168.85.134**, con el objetivo de detectar puertos abiertos sin establecer conexiones completas, haciéndolo más difícil de detectar.

- `sudo nmap -p 22 192.168.85.134`  
  Este comando escanea específicamente el puerto 22 (utilizado comúnmente para **SSH**) en la dirección IP **192.168.85.134** para ver si está abierto y qué servicios lo están utilizando.

- `sudo nmap -p 21-23,80 192.168.85.134`  
  Este comando escanea los puertos **21 a 23** (FTP, SSH, Telnet) y el puerto **80** (HTTP) en la dirección IP **192.168.85.134** para detectar qué servicios están activos en esos puertos.

- `sudo nmap -sS 192.168.85.134`  
  Este comando realiza un escaneo SYN sigiloso en la dirección IP **192.168.85.134** con el fin de detectar puertos abiertos sin ser fácilmente detectado por los sistemas de seguridad.

- `sudo nmap -sS -p- 192.168.85.134`  
  Este comando realiza un escaneo SYN sigiloso en **todos los puertos posibles** (de 0 a 65535) en la dirección IP **192.168.85.134**, buscando cualquier puerto abierto.

- `sudo nmap -sS -p 21 -O 192.168.85.134`  
  Este comando escanea el puerto **21** (FTP) utilizando un escaneo SYN sigiloso en la dirección IP **192.168.85.134**, e intenta detectar el sistema operativo del objetivo con la opción `-O`.

- `sudo nmap -sS -p- -sV 192.168.85.134`  
  Este comando realiza un escaneo SYN sigiloso en **todos los puertos posibles** de la dirección IP **192.168.85.134** y utiliza la opción `-sV` p
