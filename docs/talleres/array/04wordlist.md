---
theme: "just-the-docs"
title: "Wordlist (Diccionario)"
layout: default
nav_order: 4
parent: "ARRAY DIINF 2024"
---
# Wordlist (Diccionario)
## Descarga de rockyou
```bash
mkdir /home/lesand/Desktop/tools/diccionarios
cd /home/lesand/Desktop/tools/diccionarios
wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz
tar -xzvf rockyou.txt.tar.gz && rm rockyou.txt.tar.gz
```

## Creacion de script en python para la generacion de diccionario (palabra+numeros)
```bash
nano /home/lesand/Desktop/tools/diccionarios/wordlist.py
```
Pegar el siguiente contenido en el archivo
```python
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
```bash
cd /home/lesand/Desktop/tools/diccionarios
python3 wordlist.py  
```

## Ejemplo usando CRUNCH
Crea combinaciones de mínimo 2 y máximo 2 palabras
```bash
crunch 2 2 
```
Para guardar usamos la opción -o y el nombre del archivo.
```bash
cd /home/lesand/Desktop/tools/diccionarios
crunch 2 2 -o crunch01.txt
```
Para especificar caracteres podemos usar
```bash
crunch 4 4 abc123
```
Para ver el conjunto de caracteres usados por crunch podemos revisar el siguiente archivo:
```bash
cat /usr/share/crunch/charset.lst
```
Por defecto si no se especifica un conjunto de caracteres se usa **lalpha**, a continuacion seleccionaremos el charset por **hex-upper**:
```bash
crunch 4 4 -f /usr/share/crunch/charset.lst hex-upper
```
También podemos indicar un patrón + caracteres, números o símbolos:
* @ = lower case characters
* , = upper case characters
* % = numbers
* ^ = symbols
Ejemplo Generar un listado que comience con un numero después la palabra lesand luego un símbolo, caracter mayuscula y minuscula.
```bash
crunch 10 10 -t %lesand^@,
```
Permutar entre una lista de palabras con 10 caracteres
```bash
crunch 10 10 -p hola chao casa
```
## Creacion de diccionario (palabra+numeros) con crunch.
```bash
cd /home/lesand/Desktop/tools/diccionarios
crunch 10 10 -t lesand%%%%
```
## Ejemplo usando CEWL
```bash
cewl -m 4 -a -e -w /home/lesand/Desktop/tools/diccionarios/ejemplocewl.txt https://dpachecocl.github.io
```
Donde:
```
-m 4 : Longitud mínima de la palabra, por defecto 3
-a : Incluye metadata
-e: Incluye direcciones de email
-w /home/user/Desktop/Diccionario.txt: Escribir en archivo de texto
```
## Ejemplo usando CUPP
Lo ejecutamos y usaremos el modo interactivo.
```bash
cd /home/lesand/Desktop/tools/cupp
python3 cupp.py -i 
```
