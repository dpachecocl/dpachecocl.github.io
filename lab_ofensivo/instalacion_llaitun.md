---
theme: "just-the-docs"
title: "Instalacion de Llaitun"
layout: default
nav_order: 4
parent: "Lab Ofensivo" 
---
## Crear directorio tools para descargar herramientas desde GitHub
```
mkdir /home/lesand/Desktop/tools
cd /home/lesand/Desktop/tools
```
## Descargar Llaitun
```
git clone https://github.com/lesandcl/Llaitun.git
```
```
sudo apt-get install software-properties-common -y
sudo add-apt-repository ppa:deadsnakes/ppa -y
```
```
sudo apt-get  update
```
```
sudo apt-get install python3.7 -y
sudo apt install python3.7-distutils -y
```
```
sudo apt-get install virtualenv -y
virtualenv ENV-LLAITUN -p python3.7
source ENV-LLAITUN/bin/activate
```
```
cd /usr/lib/x86_64-linux-gnu/
sudo ln -s -f libc.a liblibc.a
```
```
cd /home/lesand/Desktop/tools/Llaitun/
pip install -r requirements.txt
```
```
sudo $(which python) Llaitun.py
```
## Desactivar ambiente virtual
Para desactivar el ambiente virtual se usa el siguiente comando
```
deactivate
```
## Activar ambiente virtual
Para activar el ambiente virtual nuevamente se usa el siguiente comando
```
cd /home/lesand/Desktop/tools/
source ENV3.7/bin/activate   
```
