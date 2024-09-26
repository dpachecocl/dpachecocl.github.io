---
theme: "just-the-docs"
title: "Wordlist"
layout: default
nav_order: 3
parent: "Herramientas"
---
# **Wordlists (Diccionario)**
## Descarga de rockyou
```bash
nanomkdir /home/lesand/Desktop/tools/diccionarios
cd /home/lesand/Desktop/tools/diccionarios
wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz
tar -xzvf rockyou.txt.tar.gz && rm rockyou.txt.tar.gz
```
## Creacion de script en python para la generacion de diccionario
```bash
nano /home/lesand/Desktop/tools/diccionarios/wordlist.py
```
Pegar el siguiente contenido en el archivo
```
# Nombre del archivo
nombre_archivo = "diccionario.txt"

# Abre el archivo en modo escritura y escribe los datos
with open(nombre_archivo, "w") as archivo:
    for numero in range(10000):
        # Formatea el número como una cadena de 4 dígitos con ceros a la izquierda
        numero_formateado = f"{numero:04}"
        # Escribe "lesand" seguido del número formateado en el archivo
        archivo.write(f"lesand{numero_formateado}\n")

print(f"Se ha creado el archivo '{nombre_archivo}' con las palabras y números.")
```
