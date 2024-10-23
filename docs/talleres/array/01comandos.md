---
theme: "just-the-docs"
title: "Comandos"
layout: default
nav_order: 1
parent: "ARRAY DIINF 2024"
---
# Comandos #
## Comandos Mikrotik
### Mostrar una lista de todas las interfaces
```
interface print
```

### Mostrar las direcciones IPs asignadas a las interfaces del router
```
ip add print
```

### Mostrar información sobre los clientes DHCP configurados en el router
```
ip dhcp-client print
```

### Liberar la IP de la interface 0
```
ip dhcp-client release 0
```
_Donde 0 representa el # de la interfaz_

### Renovar la IP de la interface 0
```
ip dhcp-client renew 0
```
_Donde 0 representa el # de la interfaz_

### Activar interface 0
```
interface enable 0
```
### Desactivar interface 0
```
interface disable 0
```
