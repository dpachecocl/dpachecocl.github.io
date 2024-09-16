---
theme: "just-the-docs"
title: "Mejoras de la Terminal"
layout: default
nav_order: 1
parent: "Ubuntu" 
---
# Mejoras de la terminal
## Actualización

**Descripción**: Actualiza la lista de paquetes disponibles y sus versiones, luego instala las últimas versiones de todos los paquetes actualmente instalados en el sistema.
```
sudo apt-get update && sudo apt-get upgrade -y
```
## ZSH,Curl,Git y Terminator

**Descripción**: Instala las herramientas básicas necesarias para el entorno de desarrollo y la terminal. ZSH es un intérprete de comandos, Curl es una herramienta para transferir datos, Git es un sistema de control de versiones y Terminator es una terminal avanzada para Linux.
```
sudo apt-get install zsh -y
sudo apt-get install curl -y
sudo apt-get install git -y
sudo apt-get install terminator -y
```

## Instalación OhMyZSH
**Descripción**: Instala Oh My Zsh, un framework de gestión para la configuración de ZSH, que proporciona temas y plugins para mejorar la experiencia en la terminal.
```
echo "Y" | sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
chsh -s $(which zsh)
```

## Instalación Powerlevel10K
**Descripción**: Descarga e instala el tema Powerlevel10k para Oh My Zsh, que mejora la apariencia visual de la terminal con información adicional y un diseño más atractivo.
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

## Configuración del tema
**Descripción**: Modifica el archivo de configuración de ZSH para establecer Powerlevel10k como el tema por defecto de la terminal.
```
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="powerlevel10k\/powerlevel10k"/' ~/.zshrc
```

## Instalación de Plugins
**Descripción**: Instala dos plugins para ZSH: "zsh-autosuggestions" ofrece sugerencias basadas en el historial de comandos, y "zsh-syntax-highlighting" añade coloreado sintáctico al escribir comandos.
```
sudo apt install zsh-autosuggestions
sudo apt install zsh-syntax-highlighting
```
## Configuración de Plugins
**Descripción**: Configura el archivo ~/.zshrc para habilitar los plugins.
```
echo "#Plugins" >> ~/.zshrc
echo "source /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
echo "source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc
```

## Descarga Fonts
**Descripción**: Descarga y mueve las fuentes MesloLGS NF a la carpeta de fuentes del sistema, luego actualiza el caché de fuentes para que estén disponibles en la terminal.
```
wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf
wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf
wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf
wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf
sudo mv MesloLGS\ NF\ *.ttf /usr/local/share/fonts/
fc-cache -fv
exit
```

* Abrir terminator (ctrl+alt+t)
* Cambiar las fonts MesloLGS
* Tamaño 12
* Ejemplo de configuracion de Powerlevel10k: YYY1Y 111 221 411 22n 1y

## Cambio de Fondo
**Descripción**: Cambia el fondo de escritorio descargando una nueva imagen y configurándola como el fondo actual utilizando gsettings.
```
cd
cd Pictures
wget https://getwallpapers.com/wallpaper/full/4/e/5/724440-free-download-ubuntu-wallpaper-hd-1920x1080.jpg
gsettings set org.gnome.desktop.background picture-uri "file://$(pwd)/724440-free-download-ubuntu-wallpaper-hd-1920x1080.jpg"
```

## Instalación Conky
**Descripción**: Instala Conky, una herramienta ligera de monitorización del sistema, que muestra información como el uso de CPU, memoria, espacio en disco, etc., en el escritorio.
```
sudo apt-get install conky-all -y
```

Crear archivo de configuración:
```
nano ~/.conkyrc
```

Pegar la siguiente información:
```
conky.config = {
    alignment = 'top_right',
    background = true,
    cpu_avg_samples = 2,
    double_buffer = true,
    draw_borders = false,
    draw_graph_borders = true,
    draw_outline = false,
    draw_shades = true,
    use_xft = true,
    font = 'DejaVu Sans Mono:size=10',
    gap_x = 50,
    gap_y = 50,
    minimum_height = 5,
    minimum_width = 200,
    net_avg_samples = 2,
    no_buffers = true,
    out_to_console = false,
    out_to_stderr = false,
    extra_newline = false,
    own_window = true,
    own_window_class = 'Conky',
    own_window_type = 'desktop',
    own_window_transparent = true,
    update_interval = 1.0,
    uppercase = false,
    use_spacer = 'none',
    show_graph_scale = false,
    show_graph_range = false
};

conky.text = [[
${color green}Uptime:
$color $uptime
${color green}CPU Usage:
$color $cpu% ${cpubar 4}
${color green}RAM Usage:
$color $memperc% ${membar 4}
${color green}Swap Usage:
$color $swapperc% ${swapbar 4}
${color green}Disk Usage:
$color ${fs_used_perc /}% ${fs_bar 4 /}
${color green}Processes: $color $processes  ${color grey}
${color green}Running: $color $running_processes

${color green}Networking:
Down: $color${downspeedf ens33} k/s ${color green}Up: $color${upspeedf ens33} k/s
${color green}Local IP:$color ${addr ens33}
${color green}Public IP:$color ${execi 300 wget -qO- http://ipecho.net/plain; echo}

${color green}Connections TCP:$color ${tcp_portmon 1 65535 count}

]];
```
Luego guardar el archivo:
- Ctrl + O: Guardar el archivo (Output).
- Enter:` Confirmar el nombre del archivo.
- Ctrl + X: Salir de nano.

## Iniciar automaticamente Conky al reiniciar el sistema
```
cd
echo -e '#!/bin/bash\nsleep 10 && conky -d' > ~/start_conky.sh
chmod +x ~/start_conky.sh
mkdir -p ~/.config/autostart
cat > ~/.config/autostart/conky.desktop <<EOL
[Desktop Entry]
Type=Application
Exec=$HOME/start_conky.sh
Hidden=false
NoDisplay=false
X-GNOME-Autostart-enabled=true
Name=Conky
Comment=Start Conky at login
EOL
```
## Reiniciar el sistema.
**Descripción**: Reiniicia el sistema.
```
reboot
```
