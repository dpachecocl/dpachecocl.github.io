---
theme: "just-the-docs"
title: "Explotacion Capa 2 y 3"
layout: default
nav_order: 19
parent: "Seguridad Ofensiva"
---
# Explotacion Capa 2 y 3
## Configuracion Mikrotik
Opcionalmente si quieres borrar el mikrotik se puede usar el siguiente comando:
```
system reset-configuration
```
Para revisar las IPs en Mikrotik
```
ip add print
```
Configuracion de interface bridge, asignacion de IP y configuracion de RIP
```
interface bridge add name=bridge1
interface bridge port add bridge=bridge1 interface=ether1
ip dhcp-client add disabled=no interface=bridge1
routing rip interface add send=v1-2
routing rip network add network=192.168.50.0/24
```
Revision de la tabla de rutas
```
ip route print
```
