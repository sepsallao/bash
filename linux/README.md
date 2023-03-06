# LINUX

# GENERAL
## NETWORKING

### Static IP
###### Setup
https://www.youtube.com/watch?v=WQyoA35jq24
How to Set Static IP in Ubuntu Server 20.04 - 
KeepItTechie

##

### SSH
###### Generate keys
`$ ssh-keygen -t rsa -b 4096 -C "sallaojoseph@hotmail.com"`

###### Use:
```
ssh sep@192.168.1.20

or better

ssh -o ServerAliveInterval=30 sep@192.168.1.17
```

##


## WEBSERVER

## INFRASTRUCTURE


## TOOLS

### ZIP and UNZIP
###### ZIP: Use
`$ zip -r file.zip path/to/directory/or/file`

###### Zip: with passowrd
`$ zip -er filename.zip path/to directory/or/file`

### LSHW
###### Use:
```
$ lshw
or 
$ sudo lshw
```

###### Export output
```
$ sudo kshw > hw.txt
or
$ sudo lshw -html > hw.html
```

##

### SCP
###### Use:
`$ scp hw.txt hw.html sep@10.0.1.200:Desktop`

##

### LSCPI
###### What for: Ports
`$ lscpi`

###### or 

###### -tv mean tree view
`$ lscpi -tv`

##

### LSCPU
###### To check the Machine's hardware specification
`$ lscpu`

##

### LSMEM
###### What for: regarding RAM's status and information
`$ lsmem`

##

### BLKID
###### What for: regarding storages
`$ blkid`

##

### FISH and Oh My Fish
###### INSTALLATION LINK
https://www.hanselman.com/blog/installing-fish-shell-on-ubuntu-on-windows-10

##

### LS
######
 ls -a ~/

##

### TAR
###### To extract a .tgz file with tar you need to use,

`$ tar -xvzf /path/to/yourfile.tgz`

##


## TROUBLESHOOTING

### IP 
###### To get the router's gateway
`$ ip route | grep default`

##

### History
###### Use:
`$ history`

###### To export
`$ history > history_for_print.txt`

##


#### Change ownership
`$ sudo chown -R $(whoami) path/of/folder/and/file`

##












#### Creating bootable disk

####### To see the device path
`$ df`
or
`$ lsblk`

### Unmount
####### as x if whatever letter it used*

`$ sudo umount /dev/sdx`

##

####### Format
`$ sudo mkfs.vfat /dev/sdx`
*as x if whatever letter it used*

####### Setup bootable device

`$ sudo dd bs=4M if=/path/to/CentOS-7-x86_64-DVD-1810.iso of=/dev/sdx status=progress oflag=sync`

##

#### VIM
####### Installation
`$ sudo apt install vim`

##

#### Hostname
####### Change Machine name:
```
$ hostnamectl set-hostname <new name>
$ reboot
```

##

#### User Name
####### Changing User name:
```
$ usermod -l [new username] -d /home/[new username] -m [old username]
$ reboot
```

##

#### Password
####### Change password:
`$ sudo passwd [username]`

##

#### Tar
####### Decrypting tar compress files
`$ tar -xvzf documents.tar.gz`

##

#### Snap
####### Install 
```
$ git clone https://aur.archlinux.org/snapd.git
$ cd snapd/
$ makepkg -si
$ sudo systemctl enable --now snapd.socket
$ sudo ln -s /var/lib/snapd/snap /snap
```

##

#### Google Chat 
####### Install with Snap
`$ sudo snap install google-chat-electron`

##

#### Remmina
####### Install with Snap
`$ sudo snap install remmina`

##

#### Spotify
####### Install with Snap
`$ sudo snap install spotify`

##

#### Mysql
####### Enable
```
$ mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
$ systemctl enable mysql.service
$ systemctl start mysql.service
```

##

#### AWS
####### Install
```
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
$ unzip awscliv2.zip
$ sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin
```

##

#### Eksctl
####### Install
```
$ curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)\_amd64.tar.gz" | tar xz -C /tmp
$ sudo mv /tmp/eksctl /usr/local/bin
$ eksctl version
```

##

#### AWS I am authenticator
####### Install
```
$ curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.21.2/2021-07-05/bin/linux/amd64/aws-iam-authenticator
$ chmod +x ./aws-iam-authenticator
$ mkdir -p $HOME/bin && cp ./aws-iam-authenticator $HOME/bin/aws-iam-authenticator && export PATH=$PATH:$HOME/bin
$ echo 'export PATH=$PATH:$HOME/bin' >> ~/.bashrc
$ aws-iam-authenticator help
```

##

#### Minikube
####### Install
```
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

##

#### Kubectl
####### Install
```
$ curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
$ sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
$ kubectl version --client
```

##



#### 'Make' install and uninstall
####### To install:
```
$ cd /path/to/the/installer
$ sudo make install
```

####### To uninstall:
`$ sudo make uninstall`

##

### IGNORE ANYTHING AFTER CLOSING LID(FOR LAPTOPS ONLY)
######
```
$ sudo vim /etc/systemd/logind.conf 

1. Find the HandleLidSwitch=suspend, and unqoute(remove '#')
2. Replace 'suspend' into 'ignore'. (the other choices 'lock', 'ignore', and 'poweroff')
3. Save and run:

$ sudo su
# systemctl restart systemd-logind.service
```
##



### CHMOD
####### Link:
`https://www.howtogeek.com/437958/how-to-use-the-chmod-command-on-linux/`

##


# ARCH: BTW I am using Arch Linux

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




# UBUNTU: Ubuntu Server
 
## APT-GET 
###### apt-get cannot connect to Ubuntu archives
 
Editing /etc/apt/sources.list worked for me. To edit, run

$ vim /etc/apt/sources.list

There you just need to replace all http://**xx**.archive.ubuntu.com/ubuntu... to http://archive.ubuntu.com/ubuntu ...

That's it. Retry

$ sudo apt-get update

##

## dpkg error
######
https://itsfoss.com/could-not-get-lock-error/

##

## Net Tools
###### Install
`$ sudo apt install net-tools`

###### ifconfig
`$ ifconfig`

##
