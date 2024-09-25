---
theme: "just-the-docs"
title: "Mikrotik"
layout: default
nav_order: 1
parent: "Coamandos OS" 
---
# **Comandos Mikrotik**
## CLI ##
### Revisar interfaces disponibles ###
```
# interface print
```
### Revisar IPs de las interfaces ###
```
# ip add print
```
### Visualizar interfaces clientes DHCP ###
```
ip dhcp-client print
```
### Liberar la IP de una interface ###
```
ip dhcp-client release 0
```
_Donde 0 representa el # de la interfaz_
### Renovar la IP de una interface ###
```
ip dhcp-client release 0
```
_Donde 0 representa el # de la interfaz_