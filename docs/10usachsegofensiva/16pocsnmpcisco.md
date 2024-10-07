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
int eth0/0
 no shutdown
 ip address dhcp
username lesand password lesand2024
enable secret lesand2024
snmp-server community lesand2024 rw
end
copy running-config startup-config
show ip int brief | inc DHCP
```
## Configuracion de router Cisco
