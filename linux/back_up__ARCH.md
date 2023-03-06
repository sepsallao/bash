# BTW I am using Arch Linux

### Pacman
###### Update
`$ pacman -Syy`

###### Update and Upgrade
`$ pacman -Syu`

###### Install packges
`$ pacman -S <package-name>`

###### Uninstall leaving dependencies
`$ pacman -R <package_name>`

###### Uninstall including dependencies
`$ pacman -Rs <package_name>`

###### The above may sometimes refuse to run when removing a group which contains otherwise needed packages. In this case try
`$ pacman -Rsu <package_name>`

###### To remove a package, its dependencies and all the packages that depend on the target package
`$ pacman -Rsc <package_name>`

###### To remove a package, which is required by another package, without removing the dependent package
`$ pacman -Rdd <package_name>`

###### Pacman saves important configuration files when removing certain applications and names them with the extension: .pacsave. To prevent the creation of these backup files use the -n option
`$ pacman -Rn <package_name>`

###### Delete all uneeded packages and dependencies
`$ sudo pacman -R $(pacman -Qdtq)`

###### List all installed packages
`$ sudo pacman -Q`

##

### Yay
###### Install 
```
$ sudo git clone https://aur.archlinux.org/yay.git
$ makepkg -si
```
##

## Google calendar
###### Install with Yay
`$ yay -S google-calendar-nativefier`

##

## Google Keep
###### Install with Yay
`$ yay -S google-keep-nativefier`

##

## Google Messages
###### Install with Yay
`$ yay -S google-messages`

##

### Viber
###### Install with Yay
`$ yay -S viber`

##

### headsetcontrol
###### Install with Yay
`$ yay -S headsetcontrol`

##

### colorpicker
###### Install with Yay
`$ yay -S colorpicker`

##

### Net Tools: for ifconfig
###### Install
`$ sudo pacman -S net-tools`

## 

### Vim
###### Install
`$ sudo pacman -S vim`

##

### Ignore Lid
###### Open to modify logind config file
`$ sudo vim /etc/systemd/logind.conf`

###### Uncomment or Write below
```
HandleLidSwitch=ignore
```

###### Open to modify UPower config file
`$ sudo vim /etc/UPower/UPower.conf`

###### Uncomment or Write below
```
IgnoreLid=true
```

###### Update and reboot:
```
$ sudo pacman -Syy
$ reboot
```

##

### Neofetch
###### Install 
`$ sudo pacman -S neofetch`

##

### Discord
###### Install
`$ sudo pacman -S discord`

##

### VSCode
###### Install
`$ sudo pacman -S code`

##

### VLC
###### Install 
`$ sudo pacman -S vlc`

##

### LM Sensors
###### Install:
`$ sudo pacman -S lm_sensors`

###### First run for detecting hardwares:
`$ sudo sensors-detect`

###### To run:
`$ sudo sensors`

##

### Base Devel: Makepkg
###### Install
`$ sudo pamac install base-devel`

##

### Brave browser
###### Install
`$ sudo pacman -S brave-browser`

##

### Libre Office
###### Install 
`$ sudo pacman -S libreoffice-fresh`

##

### Telegram Desktop
###### Install
`$ sudo pacman -S telegram-desktop`

##

### Anydesk
###### Install 
`$ sudo pacman -S anydesk-bin`

##

### GIT
###### Install
`$ sudo pacman -S git`

###### To see version
`$ git --version`

###### Create new branch
`$ git checkout -b <branch name>`

###### To go on the branches avaliable locally
`$ git checkout <branch name>`

##

### Terraform
###### Install
`$ sudo pacman -S terraform`

###### Use 
`$ terraform -help`

##

### Python
###### Install
`$ sudo pacman -S python`

###### Use
```
$ python -v
or
$ python3 -v
```

##

### Ansible
###### Install 
`$ sudo pacman -S ansible`

###### Use
`$ ansible`

##

### NodeJS
###### Install
`$ sudo pacman -S nodejs`

##

### MLocate
###### Install
`$ sudo pacman -S mlocate`

##

### Alacritty Terminal Emulator
###### Install
```
$ sudo pacman -S alacritty
$ mkdir ~/.config/alacritty/
$ cp /usr/shr/doc/alacritty/alacritty.yml ~/.config/alacritty/
```

##

### Youtube DL
###### Install
`$ sudo pacman -S youtube-dl`

###### Use
`$ youtube-dl <youtube-url.com/code123>`

##

### Xprop
###### Install
`$ sudo pacman -S xprop`

###### Use: to get the class of open and running applications
`$ xprop`

##

### Uname
###### Use: To see what linux kernel currently using
`$ uname -r`

### Linux Headers
###### Install
`$ sudo pacman -S linux-headers`

##

### Xrandr
###### Use
`$ xrandr --output HDMI1 --mode 1920x1080`

##

### FFMPEG
###### Install
`$ sudo pacman -S ffmpeg`

###### Use: to convert mpeg2/ts files
`$ ffmpeg -i <file-name.ts/mpeg> -c:v libx264 -crf 0 -c:a copy output.mp4`

##

### Go Language
###### Install
`$ sudo pacman -S go`

##

### MySQL Workbench
###### Install
`$ sudo pacman -S mysql-workbench`

##

### QBittorrent
######
`$ sudo pacman -S qbittorrent`

##

### NTFS
######
`$ sudo pacman -S ntfs-3g`
sudo vim fstab
##

### Tree
###### Install
`$ sudo pacman -S tree`

##

### Qalculate-gtk
###### Install
`$ sudo pacman -S qalculate-gtk`

##

### Unclutter
###### Install
`$ sudo pacman -S unclutter`

##

### Xresources
###### Install
`$ sudo pacman -S xorg-xrdb`

###### Create config file
`$ xrdb ~/.Xresources`

##

### Thunderbird
###### Install
`$ sudo pacman -S thunderbird`

##

### Pipewire and Pavucontrol
###### Install
```
$ sudo pacman -S pipewire pipewire-puls pipewire-alsa pavucontrol
$ sudo pacman -S  pipewire-media-session
```

```
pactl set-sink-mute 0 toggle
pactl set-sink-volume 0 +5%
```

##

### Xbacklight
###### fix this soon
```
sudo vim /etc/modprobe.d/i915.conf
sudo pacman -S  xf86-video-intel
sudo pacman xf86-video-intel
sudo vim modesetting.conf
sudo vim 20-modesetting.conf
vim 20-modesetting.conf
sudo vim /etc/X11/xorg.conf.d/20-modesetting.conf
xbacklight
xbacklight -inc 10; notify-send 'brightness up'
sudo pacman -S xorg-xbacklight
man xfpm-power-backlight-helper
xfpm-power-backlight-helper --help
xfpm-power-backlight-helper
```
##

### Unzip
###### Install
`$ sudo pacman -S unzip`

##

### Proton VPN
###### Install
```
$ pamac update --force-refresh
$ pamac search --aur protonvpn
$ pamac build protonvpn

# if asked for pgp keys, paste this:
 A884 41BD 4864 F95B EE08 E63A 71EB 4740 1994 0E11
```

###### Uninstall
`$ pamac remove protonvpn`

###### For more, check documentation:
https://protonvpn.com/support/official-linux-client-arch/

##

### OpenSSH for WSL2 Arch
###### Install: this also includes ssh-keygen command 
`$ sudo pacman -S openssh`

##

### Python SSH pubkeys (NEED SOME TEST)
###### Install
`$ sudo pacman -S python-sshpubkeys`
