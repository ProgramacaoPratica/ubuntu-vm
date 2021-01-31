# Ubuntu 20.04 LTS no VirtualBox

### Resolução de tela no Ubuntu
- Show Applications -> Settings -> Displays -> Resolution
- Abrir editor como root: sudo gedit
- Criar script "screen.sh" e salvar na pasta /usr/local/sbin
  - Conferir: cat /usr/local/sbin/screen.sh
- Permissão para executar: sudo chmod +x screen.sh
- Criar arquivo "screen.desktop" na pasta ~/.config/autostart
  - Conferir: abrir app startup

## Códigos utilizados

```
xrandr --newmode "1920x1080"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync
xrandr --addmode Virtual1 1920x1080
xrandr --output Virtual1 --mode 1920x1080
```

```
[Desktop Entry]
Type=Application
Exec=/usr/local/sbin/screen.sh
Hidden=false
NoDisplay=false
Name=Screen Full HD
X-GNOME-Autostart-enabled=true
```
