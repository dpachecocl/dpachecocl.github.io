---
theme: "just-the-docs"
title: "Instalacion Llaitun"
layout: default
nav_order: 5
parent: "Seguridad Ofensiva"
---
## Crear directorio tools para descargar herramientas desde GitHub
```bash
mkdir /home/lesand/Desktop/tools
cd /home/lesand/Desktop/tools
```
## Descargar Llaitun
```bash
git clone https://github.com/lesandcl/Llaitun.git
```
```bash
sudo apt-get install software-properties-common -y
sudo add-apt-repository ppa:deadsnakes/ppa -y
```
```bash
sudo apt-get  update
```
```bash
sudo apt-get install python3.7 -y
sudo apt install python3.7-distutils -y
```
```bash
sudo apt-get install virtualenv -y
virtualenv ENV-LLAITUN -p python3.7
source ENV-LLAITUN/bin/activate
```
```bash
cd /usr/lib/x86_64-linux-gnu/
sudo ln -s -f libc.a liblibc.a
```
```bash
cd /home/lesand/Desktop/tools/Llaitun/
pip install -r requirements.txt
```
```bash
sudo $(which python) Llaitun.py
```
## Desactivar ambiente virtual
Para desactivar el ambiente virtual se usa el siguiente comando
```bash
deactivate
```
## Activar ambiente virtual
Para activar el ambiente virtual nuevamente se usa el siguiente comando
```bash
cd /home/lesand/Desktop/tools/
source ENV-LLAITUN/bin/activate
```
