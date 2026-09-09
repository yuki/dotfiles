# Dotfiles

Estos son mis ficheros de configuración, principalmente para mi equipo con [Arch Linux](https://archlinux.org/).

La gestión de los dotfiles la hago con [YADM](https://yadm.io/). Algunos de ellos se pueden reutilizar en otros sistemas operativos, como .gitconfig.

## Paquetes a instalar

Los paquetes que necesito en mi día a día:

- base:
  - git base-devel neovim terminator yadm zsh etckeeper podman podman-compose podlet qemu-full virt-manager nvidia-settings firefox syncthing nvidia-container-toolkit
  - instalar/configurar [Oh My Zsh](https://ohmyz.sh/)
  - activar etckeeper

- [yay](https://github.com/Jguer/yay) para AUR:
```
git clone https://aur.archlinux.org/yay-bin.git
cd yay-bin
makepkg -si
```

- hyprland como windowmanager:
  - mako waybar hyprpaper hyprpolkitagent ttf-nerd-fonts-symbols ttf-nerd-fonts-symbols-mono ttf-sourcecodepro-nerd satty hyprshot fuzzel hyprqt6engine hypridle hyprlock

- otros:
  - gamemode steam telegram-desktop fuse2 nvtop python-pip vlc vlc-plugins-extra vlc-plugin-dvd vlc-plugin-bluray vlc-plugin-x265


## Servicios a configurar

Tengo varios servicios que deben estar corriendo y configurando:

- syncthing:
    - **el más importante!** para backups remotos: `systemctl --user enable syncthing && systemctl --user start syncthing` y luego configurar los remotos.
- gamemode: para juegos.
    - `systemctl --user enable gamemode`
- arranque de pods automáticamente sin login
    - `loginctl enable-linger $USER`
- **libvirtd** para virtualización
    - `systemctl enable libvirtd.service`
 
