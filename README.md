# Ubuntu 20.04 LTS no VirtualBox

### Resolução de tela no Ubuntu
- Show Applications -> Settings -> Displays -> Resolution
- Abrir editor como root: $ sudo gedit
- Criar script "screen.sh" e salvar na pasta /usr/local/sbin (Adicione no arquivo o código abaixo: "Habilitar resolução Full HD")
  - Conferir: entrar na pasta onde foi salvo o arquivo digitando o código no terminal $ cd /usr/local/sbin
  - Tente rodar o script no terminal $ ./screen.sh
  - Irá mostraruma mensagem de erro de permissão
- Para adicionar permissão para executar o script, digite no terminal: $ sudo chmod +x screen.sh
- Rode novamente o script no terminal $ ./screen.sh
- Será exibida a janela em full HD, entretando, será necessário rodar este script toda vez que a VM é iniciada. Para alterar isso vamos criar um script de inicialização.
- Criar arquivo "screen.desktop" na pasta ~/.config/autostart (Adicione no arquivo o código abaixo: "Aplicar resolução Full HD na inicialização")
  - Conferir: abrir app startup
  
## Códigos utilizados

### Habilitar resolução Full HD

```
xrandr --newmode "1920x1080"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync
xrandr --addmode Virtual1 1920x1080
xrandr --output Virtual1 --mode 1920x1080
```

### Aplicar resolução Full HD na inicialização
```
[Desktop Entry]
Type=Application
Exec=/usr/local/sbin/screen.sh
Hidden=false
NoDisplay=false
Name=Screen Full HD
X-GNOME-Autostart-enabled=true
```

