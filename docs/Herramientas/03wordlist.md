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
```
cd /home/lesand/Desktop/tools/diccionarios
python3 wordlist.py  
```
### Ejemplo usando CRUNCH

Crea combinaciones de mínimo 2 y máximo 2 palabras
```
crunch 2 2 
```

Para guardar usamos la opción -o y el nombre del archivo.
```
cd /home/lesand/Desktop/tools/diccionarios
crunch 2 2 -o crunch01.txt
```

Para especificar caracteres podemos usar
 ```
 crunch 4 4 abc123 -o crunch02.txt
```

Para ver el conjunto de caracteres usados por crunch podemos revisar el siguiente archivo:
```
cat /usr/share/crunch/charset.lst
```

Por defecto si no se especifica un conjunto de caracteres se usa **lalpha**, para seleccionar el charset por **hex-upper**:
```
crunch 4 4 -f /usr/share/crunch/charset.lst hex-upper
```
También podemos indicar un patrón + caracteres, números o símbolos:
* @ = lower case characters
* , = upper case characters
* % = numbers
* ^ = symbols
*Ejemplo Generar un listado que comience con un numero después la palabra lesand luego un símbolo, caracter mayuscula y minuscula.
```
crunch 10 10 -t %lesand^@,
```

Permutar entre una lista de palabras con 10 caracteres
```
crunch 10 10 -p hola chao casa
```
