---
theme: "just-the-docs"
title: "Ejemplos Scapy"
layout: default
nav_order: 18
parent: "Seguridad Ofensiva"
---
# Scapy
## Ejecucion de modo interactivo.
`sudo scapy`
## Funciones basicas
- `ls()` : Lista los protocolos disponibles en scapy.
- `lsc()` : Lista los comandos disponibles en scapy.
- `send` : Envia PDU en layer 3
- `sendp` : Envia PDU en layer 2
## Crear PDU (capa 2)
- `PDU = Ether()/IP()/ICMP()/"dpacheco"`
## Crear PDU (capa 2)
- `sendp(PDU)`
## Crear y enviar PDU (capa 2)
- `sendp(Ether()/IP(dst="8.8.8.0",src="1.1.1.1")/ICMP()/"dpacheco")`
## Revisar contenido de una PDU
- `PDU.show()`
## Revisar campo especifico de una PDU
- `PDU.src`
- `PDU.ttl`
## Cambiar valor de un campo
- `PDU.ttl=123`
## Crear y enviar una PDU de capa 3
- `PDUL3 = IP(dst="8.8.8.8")/ICMP()/"dpacheco"`
- `send(PDUL3)`
## Leer una captura y almacenarla en una variable
- `CAP=rdpcap("Captura01.pcapng")`
## Ver el primer mensaje capturado
- `CAP[0]`
- `CAP[0].show()`

