---
theme: "just-the-docs"
title: "Instalacion Docker & Selenium"
layout: default
nav_order: 6
parent: "Seguridad Ofensiva"
---

## Instalación de Docker

### Configuración del repositorio APT de Docker
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

### Instalación de los paquetes de Docker
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

### Verificación de la instalación de Docker (ejecutando la imagen `hello-world`)
```bash
sudo docker run hello-world
```

## Instalación de Selenium en un entorno virtual

### Creación del entorno virtual
```bash
cd /home/lesand/Desktop/tools/
virtualenv ENV-SELENIUM -p python3
source ENV-SELENIUM/bin/activate
```

### Instalación de Selenium en el entorno virtual
```bash
pip install selenium
```

### Ejecución de un contenedor Docker con Selenium Chrome
```bash
sudo docker run -d -p 4444:4444 --name selenium-chrome selenium/standalone-chrome
```

## Creación de directorio para almacenar los scripts de Selenium
```bash
mkdir /home/lesand/Desktop/tools/selenium
cd /home/lesand/Desktop/tools/selenium 
```

## Creación de script de prueba

### Crear el archivo
```bash
nano selenium01.py
```

### Contenido del script
```python
# Importación de las librerías necesarias.
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options

# Configurar las opciones del navegador
options = Options()
options.add_argument('--no-sandbox')
options.add_argument('--headless')
options.add_argument('--disable-dev-shm-usage')

# Crear una instancia del navegador remoto
driver = webdriver.Remote('http://localhost:4444/wd/hub', options=options)

try:
    # Navegar a la página web deseada
    driver.get('https://www.lesand.cl')

    # Imprimir el título de la página
    print(driver.title)
finally:
    # Cerrar el navegador
    driver.quit()
```

## Desactivar el ambiente virtual
```bash
deactivate
```

## Detener el contenedor Docker de Selenium
```bash
sudo docker stop selenium-chrome
```

## Activar el ambiente virtual nuevamente

### Activar el entorno virtual
```bash
cd /home/lesand/Desktop/tools/
source ENV-SELENIUM/bin/activate
```

### Iniciar el contenedor Docker de Selenium
```bash
sudo docker start selenium-chrome
```

## Comprobación del contenedor Docker
```bash
sudo docker ps
```
