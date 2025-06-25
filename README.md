# Tutorial para instalar xfce4 en Debian

En el proceso de instalación asegurarse de desmarcar las opciones de **Entorno de Gnome** y **Gnome**
![Selección de programas](img/seleccion-programas.png)

Al reiniciar iniciar sesión
Comandos a usar

**Instalar xfce4**
```bash
sudo apt install xfce4
```
Plugins utiles
Portapapeles
```bash
sudo apt install xfce4-clipman-plugin
```
Menu de aplicaciones Whisker
```bash
sudo apt install xfce4-whiskermenu-plugin
```

## Instalación de NetworkManager
instalar NetworkManager
```
sudo apt install network-manager-gnome
```
**Configurar Red**
```bash
sudo nano /etc/network/interfaces
```
Comentar esta parte
```
#allow-hotplug wlo1
#iface wlo1 inet dhcp
#       wpa-ssid A15 de Sergio
#       wpa-psk  sergio111
```
Configurar Netwok Manager
```
[main]
plugins=ifupdown,keyfile

[ifupdown]
managed=false
```
reiniciar network manager o simplemente reiniciar sistema:
```
sudo systemctl restart NetworkManager
```

## Configurar inicio de sesión
Configurar iicio de sesión
```bash
sudo apt install lightdm-gtk-greeter
```
Para lograr que Debian con XFCE4 te pida solo la contraseña al iniciar sesión (es decir, que el nombre de usuario ya esté pre-seleccionado o auto-completado), debes configurar tu gestor de inicio de sesión.
``` bash
sudo nano /etc/lightdm/lightdm.conf
```
```conf
[SeatDefaults]
autologin-user=tu_nombre_de_usuario
greeter-hide-users=false
```
```
sudo systemctl restart lightdm
```
## Instalación de Flatapk
```bash
sudo apt install flatpak
```
```
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```
## Instalación de Snap
```bash
sudo apt install snapd
```
```bash
sudo snap install snapd
```
Integracion 
``` bash
sudo ln -s /var/lib/snapd/desktop/applications /usr/share/applications/snapd
```