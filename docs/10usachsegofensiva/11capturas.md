---
theme: "just-the-docs"
title: "NMAP"
layout: default
nav_order: 2
parent: "Herramientas"
---
# Captura 01: Plano de administracion
Descargue la siguiente captura y busque información importante relacionada con el proceso de reconocimiento:
[Captura01](https://github.com/dpachecocl/dpachecocl.github.io/raw/refs/heads/main/docs/capturas/Captura01.pcapng)

**Objetivos:** Identificar contraseñas en texto plano, cifradas o hashes e informacion relevante para el proceso de reconocimiento.
**Desarrollo:**
- Identificar usuario: lesand y password: lesand2022 en la sesión FTP
- Descargar archivo de configuración enviado por FTP
- Información de los dispositivos enviada por CDP
- Descargar archivo de configuración enviado por TFTP
- Identificar usuario: lesand y password: lesand2022 de la VTY en la sesión TELNET
- Identificar la password para acceder al modo privilegiado en la sesión TELNET.
- De los archivos descargados identificar la siguiente información:
```
ip ftp username lesand
ip ftp password 7 151E0E1F05242F76786167
username lesand password 7 10420C0A041916595C5678
username usuario1 secret 5 $1$uumX$4iDPCazWt.4qdJ5VYlakF/
username usuario2 secret 9 $9$XdLjmPYCuppgvM$Js4qrU4S9d.8dsTozShD24X3oZRj4Er/0AZPIspHp9I
username usuario3 secret 8 $8$I2yTFYHY9vJDaM$ZqDV0iy5F/qCdV4QkwVCqbRgd6q8uTzmAoHfOBC2Zgk
```
