---
theme: "just-the-docs"
title: "Ejemplos Python"
layout: default
nav_order: 17
parent: "Seguridad Ofensiva"
---
# Python 3
## `print`
### Ejemplo 1
imprimir un texto
```python
print("hola")
```
**resultado:**
```
hola
```
### Ejemplo 2
imprimir el contenido de una variable
```python
variable1="hola"
print(variable1)
```
**resultado:**
```
hola
```
### Ejemplo 3
imprimir varios argumentos
```python
variable1="hola"
variable2="como"
print(variable1,variable2,"estas?")
```
**resultado:**
```
hola como estas?
```
### Ejemplo 4
imprimir varios argumentos concatenando cadenas.
```python
variable1="hola"
variable2="como"
resultado = variable1 + " " + variable2 + " estas?" 
print(resultado)
```
**resultado:**
```
hola como estas?
```

## `def`
Permite definir una función, se debe indicar el nombre de la función y se pueden incluir entre paréntesis los parámetros seguido de dos puntos. Las funciones son bloques de código reutilizables que pueden tomar argumentos
### Ejemplo 1:
Crear una función que sume e imprima 2 números.
Creamos un archivo `.py` y lo ejecutamos con el siguiente contenido:
```python
def ASD(a, b):
    suma = a + b
    print(suma)
ASD(1, 2 )
```
**Resultado:**
```
3
```
### Ejemplo 2: 
Crear una función que sume e imprima 2 números, concatenando valores en `print`.

Creamos un archivo `.py` y lo ejecutamos con el siguiente contenido:
```python
def ASD(a, b):
    suma = a + b
    print("la suma de:",a,"+",b,"+","es:",suma)
ASD(1, 2 )
```
**Resultado:**
```
la suma de: 1 + 2 + es: 3
```

## `for`
La función `for` en python  se usa para iterar sobre una secuencia (como una lista, una tupla, un diccionario, un conjunto o una cadena)
### Ejemplo 1 (lista):
Creamos un archivo `.py` y lo ejecutamos con el siguiente contenido:
```python
numeros = ["uno", "dos", "tres"]
for numero in numeros:
    print(numero)
```
**Resultado:**
```
uno
dos
tres
```
**Nota:** 
- **`numeros`**: Es la lista completa sobre la cual se está iterando. Contiene todos los elementos que se procesarán en el bucle.
- **`numero`**: Es una variable temporal que toma cada uno de los valores de la lista `numeros` en cada iteración del bucle. Es decir, en la primera iteración, `numero` será `"uno"`, en la segunda iteración será `"dos"`, y en la tercera iteración será `"tres"`.
### Ejemplo 2 (lista):
Creamos un archivo `.py` y lo ejecutamos con el siguiente contenido:
```python
palabra = "Lesand"
for letra in palabra:
    print(letra)
```
**Resultado:**
```
L
e
s
a
n
d
```
### Ejemplo 3.1 (range):
Creamos un archivo `.py` y lo ejecutamos con el siguiente contenido:
```python
for x in range(5):
    print(x)
```
**Resultado:**
```
0
1
2
3
4
```
### Ejemplo 3.2 (range):
Creamos un archivo `.py` y lo ejecutamos con el siguiente contenido:
```python
for x in range(5,15):
    print(x)
```
**Resultado:**
```
5
6
7
8
9
10
11
12
13
14
```
### Ejemplo 3.2 (Iterar de un archivo):
**Crear un archivo:** Crearemos un archivo con 4 palabras para el ejemplo.
```bash
echo -e "uno\ncasa\narbol\nauto" > archivo.txt
```

```python
with open('archivo.txt', 'r') as archivo:
    for linea in archivo:
        palabra = linea.strip()
        print(palabra)

```
