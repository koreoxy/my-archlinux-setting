# My Arch Linux Setting

## My Setup Image
![THTUHU](https://github.com/user-attachments/assets/b35539f7-79ae-4740-99c5-bf22af777f33)

![newdesk](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/260b0325-e2be-4b83-830c-33c0641a9889)

![idk](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/4779290a-28a6-42da-974c-e3eccf0e2fbd)



## Jump to

- [My Arch Linux Setting](#my-arch-linux-setting)
  - [My Setup Image](#my-setup-image)
  - [Jump to](#jump-to)
  - [Command Arch Linux](#command-arch-linux)
  - [Active Dual Monitor with xrandr](#active-dual-monitor-with-xrandr)
  - [Connect Wifi for Laptop](#connect-wifi-for-laptop)
  - [Keybind DWM](#keybind-dwm)
  - [My Config file .bashrc](#my-config-file-bashrc)
  - [Install Arch Linux](#install-arch-linux)
  - [Post Install Arch Linux](#post-install-arch-linux)
  - [Install Window Manager dwm](#install-window-manager-dwm)
    - [Patching dwm](#patching-dwm)
    - [File .xinitrc](#file-xinitrc)
    - [Install Font](#install-font)
    - [Set wallpaper](#set-wallpaper)
    - [Opacity or blur terminal](#opacity-or-blur-terminal)
    - [Generate Color theme with pywal](#generate-color-theme-with-pywal)
- [Install App](#install-app)
  - [Install Flashdisk NTFS](#install-flashdisk-ntfs)
  - [Install and Update Discord](#install-and-update-discord)
  - [Install alacritty (terminal)](#install-alacritty-terminal)
  - [Install Docker](#install-docker)
  - [Install bat (for cat display)](#install-bat-for-cat-display)
  - [Install fzf (Fuzzy Finder)](#install-fzf-fuzzy-finder)
  - [Install Audio](#install-audio)
  - [Install Kdenlive](#install-kdenlive)
  - [Install GIMP](#install-gimp)
  - [Install krita](#install-krita)
  - [Install Virtualbox](#install-virtualbox)
  - [Install Mysql and MySQL Workbench](#install-mysql-and-mysql-workbench)
  - [Install xampp and configuration](#install-xampp-and-configuration)
  - [Edit file virtual host on Apache XAMPP](#edit-file-virtual-host-on-apache-xampp)
  - [Install Composer](#install-composer)
  - [Change Languages Arch Linux](#change-languages-arch-linux)
  - [Backup file .xinitrc manjaro-linux](#backup-file-xinitrc-manjaro-linux)
- [Fix Error In Arch Linux](#fix-error-in-arch-linux)
  - [Fix unable to lock database](#fix-unable-to-lock-database)
- [Command terminal perhaps help me](#command-terminal-perhaps-help-me)
  - [Set audio volume from terminal](#set-audio-volume-from-terminal)


## Command Arch Linux

| Command                                      | Description                   |
| :------------------------------------------- | :---------------------------- |
| xrandr                                       | Check list resolution monitor |
| xrandr --output "Virtual-1" --mode 1920x1080 | Change resolution monitor     |

</br>
<hr>

## Active Dual Monitor with xrandr

1. Check List Monitor
```vim
xrandr
```

2. Set Active
```vim
xrandr --output HDMI-1 --mode 1280x720 --left-of VGA-1 --output VGA-1 --mode 1366x768 --primary
```

3. Increse Brightness Monitor
```vim
xrandr --output HDMI-1 --brightness 1.2
```

</br>
<hr>


## Connect Wifi for Laptop

1. insert 
```cli
# iwctl
```

2. show wlan
```cli
# station wlan0 show
```

3. scan wlan
```cli
# station wlan0 scan
```

4. connect wlan wifi
```cli
# station wlan0 connect name_wifi
```

Using nmcli
1. List device wifi
```vim
nmcli device wifi list
```

2. Rescan device wifi
```vim
nmcli device wifi rescan
```

3. Connect wifi
```vim
nmcli device wifi connect access_point_name password your_password
```

4. Show connection
```vim
nmcli connection show
```


</br>
<hr>

## Keybind DWM

| Keybind               | Description                                                 |
| :-------------------- | :---------------------------------------------------------- |
| ALT + SHIFT + ENTER   | Open terminal                                               |
| ALT + J               | Toggle forward and backward between window viewing FORWARD  |
| ALT + K               | Toggle forward and backward between window viewing BACKWARD |
| ALT + SHIFT + c       | Close Window on active                                      |
| ALT + p               | Run program with dmenu                                      |
| ALT + 1 2 3 4         | Move workspace                                              |
| ALT + SHIFT + 1 2 3 4 | Move window to different workspace                          |
| ALT + h               | move space window to left                                   |
| ALT + l               | move space window to right                                  |
| ALT + d               | Move window to down                                         |
| ALT + i               | Move window to up                                           |
| ALT + SPACE           | Change mode window to float                                 |
| ALT + B               | hide top bar dmenu                                          |
| CTRL + SHIFT PgUp     | zoom in and zoom in terminal                                |
| CTRL + SHIFT + pgDn   | zoom in and zoom out terminal                               |

</br>
<hr>

## My Config file .bashrc

```bash
function cdf() {
    cd "$(find * -type d | fzf)"
}

alias sn='sudo shutdown now'

n() {
  nvim "$@"
}

```

</br>
<hr>

## Install Arch Linux

1. synchronizing package database

```cli
# pacman -Syy
```

2. check partition

```cli
# lsblk
```

3. format partition

```cli
# gdisk /dev/"name disk"
# gdisk /dev/sda
```

Output :
![VirtualBoxVM_XdpMEIa01p](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/6193f2ee-2793-4961-bca6-ef00ce1e46d4)

4. install archlinux keyring package

```cli
# pacman -S archlinux-keyring
```

5. update package

```cli
# pacman -Sy archinstall
```

6. trigger installation

```cli
# archinstall
```

Output Image :

- Setup Partition :
  ![VirtualBoxVM_uCfvdjegzd](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/0247935f-c055-4170-9e88-4c31da1d813b)
  ![bPtMg06mBr](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/60c4b0c2-ebf1-421e-b9a3-a32f356ef796)
- Aditional Package :
  ![M72VmRaGBI](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/86e07e4c-c963-4680-9b20-aa21739a9e91)
- All Setting Installation :
  ![VirtualBoxVM_k5i7UXRfhE](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/608888a8-a93e-44a3-a0db-64a939ea7553)

7. After installation done reboot or shutdown computer

```cli
# reboot
# shutdown now
```

<hr>

</br>

## Post Install Arch Linux

- Change session cli to dekstop environment `ALT F1 or F2`
- Upadate all package

```cli
# sudo pacman -Syu
```

- Install app

```cli
# sudo pacman -S firefox
```

- Install yay package

```cli
# git clone https://aur.archlinux.org/yay-bin.git
# cd yay-bin
# makepkg -si

// install app with yay
# yay -S firefox
```

- Install xorg for graphics

```cli
# sudo pacman -S xorg
```

- Install desktop environment (KDE Plasma)

```cli
# sudo pacman -S plasma-desktop
```

- Install xorg-xinit

```cli
# sudo pacman -S xorg-xinit
```

- Add script file .bash_profile

```cli
# vim .bash_profile

// Add script
if [ -z "${DISPLAY}"] && [ "${XDG_VTNR}" -eq 1 ]; then
    exec startx
fi
```

- Edit file xinitrc

```cli
# vim .xinitrc

// Add script
exec startplasma-x11
```

- Install konsole terminal KDE

```cli
# sudo pacman -S konsole
```

- Install fonts

```cli
# sudo pacman -S gnu-free-fonts noto-fonts ttf-jetbrains-mono
```

<hr>

</br>

## Install Window Manager dwm

reference : https://dwm.suckless.org/

1. clone dwm

```cli
# git clone https://git.suckless.org/dwm
```

2. clone dmenu

```cli
# git clone https://git.suckless.org/dmenu
```

3. clone st

```cli
# git clone https://git.suckless.org/st
```

4. create folder

```cli
# mkdir suckless
```

5. move file dwm, dmenu and st to folder suckless

```cli
# mv dwm dmenu st suckless/
```

6. open file dwm, dmenu and st and install

```cli
# cd dwm
# sudo make clean install
```

7. edit script file .xinitrc (Home directory)

```cli
# vim .xinitrc

// Add script
#exec startplasma-x11
exec dwm
```

8. Keybind dwm

- Open terminal `ALT + SHIFT + ENTER`
- Toggle forward and backward between window viewing FORWARD = `ALT + J`, BACKWARD = `ALT + K`
- Close Window on active `ALT + SHIFT + c`
- Run program with dmenu `ALT + p`
- Move workspace `ALT + 1 2 3 4`
- Move window to different workspace `ALT + SHIFT + 1 2 3 4`
- move space window to left `ALT + h`, right `ALT + l`
- Move window to down `ALT + d` to left `ALT + i`
- Change mode window to float `ALT + SPACE`
- hide top bar dmenu `ALT + B`
- zoom in and zoom out in terminal `CTRL + SHIFT PgUp` and `CTRL + SHIFT + pgDn`

</br>

### Patching dwm

1. Download patches : https://dwm.suckless.org/patches/
2. create folder in `suckless/dwm/patches`
3. copy file config `cp config.h config.def.h`
4. install patch `patch -i patches/dwm-name-version.diff`
5. after isntall patch `sudo make clean install` on folder dwm

</br>

### File .xinitrc

```bash
~/.fehbg &
xrandr --output "Virtual-1" --mode 1280x720 &
picom &
slstatus &

#exec startplasma-x11
exec dwm

```

</br>

### Install Font

#### Font Hack
```vim
sudo pacman -S ttf-hack
```

#### Font Awesome
```vim
sudo pacman -S ttf-font-awesome
```


#### Font Jetbrains
```vim
sudo pacman -S ttf-jetbrains-mono
```

#### Font Nerd Fonts symbols
```vim
sudo pacman -S ttf-nerd-fonts-symbols
```

#### Font Korean
```vim
sudo pacman -S ttf-baekmuk
```

</br>


### Set wallpaper

see general command `man feh`

1. install feh `sudo pacman -S feh`
2. set wallpaper `feh --bg-scale Pictures/name-wallpaper`

</br>

### Opacity or blur terminal

1. install picom `sudo pacman -S picom`
2. run picom `picom &`
3. open folder xdg `cd /etc/xdg/`
4. open file picom.conf `sudo vim picom.conf`
5. add script :

![A83RxMDKBu](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/2af04cc3-f975-4fcf-bd8c-e06ec72ff5cc)
![QD7shlnnWe](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/24e2abb8-743c-44f3-b2b6-90e416a158fe)
![VirtualBoxVM_wDM4tCMHF3](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/d0a35950-8185-4e41-88e1-e7b254686457)

</br>

### Generate Color theme with pywal

reference : https://github.com/dylanaraps/pywal

1. Install pywwal `sudo pacman -S python-pywal`
2. generate color wallpaper which is being used `wal -i wallpaper/name-wallpaper.png`
3. open `cd .cache/wal` to see color results
4. add `#include "/home/<USER>/.cache/wal/colors-wal-dwm.h"` in file `config.h` on folder `/dwm`

<hr>

</br>

# Install App


### Install Flashdisk NTFS
1. install package ntfs
   ```bash
   sudo pacman -S ntfs-3g
   ```
3. install package Automount
   ```bash
   sudo pacman -S udiskie
   ```
5. add command in .xinit file
   ```bash
   udiskie &
   ```
<hr>

</br>

### Install and Update Discord

1. Unduh file .tar.gz dari situs resmi Discord:
🔗 https://discord.com/download
Pilih versi "Linux" → tar.gz.

2. Ekstrak file yang telah diunduh
Gunakan perintah berikut untuk mengekstrak file:
```bash
tar -xvzf discord-*.tar.gz
```

3. Pindahkan ke direktori sistem
Hapus versi lama (jika ada) dan pindahkan yang baru:
```bash
sudo rm -rf /opt/discord
sudo mv discord /opt/
```
Note :
Untuk mengganti nama folder di terminal Linux, gunakan perintah berikut:
```bash
mv nama_folder_lama nama_folder_baru
```

</br>

### Install alacritty (terminal)
- reference : https://github.com/alacritty/alacritty/blob/master/INSTALL.md
- Theme : https://github.com/alacritty/alacritty-theme

1. First, On Arch Linux, you need a few extra libraries to build Alacritty. Here's a pacman command that should install all of them. If something is still found to be missing, please open an issue.
```bash
pacman -S cmake freetype2 fontconfig pkg-config make libxcb libxkbcommon python
```

2.  Install
```bash
sudo pacman -S alacritty
```

3. Customize setting alacritty
create file on folder `~/.config/alacritty/alacritty.toml`
```toml
[font]
normal = {family = "Hack", style = "Regular"}
bold = {family = "Hack", style = "Bold"}
size = 12

[window]
opacity = 1
blur = true
```


</br>

### Install Docker

**A. Install and Running Dcoker**

1. install docker

```bash
sudo pacman -S docker -y
```

2. check version docker

```bash
docker --version
```

3. install docker desktop, first download docker desktop for arc linux. link : https://docs.docker.com/desktop/release-notes/
4. and install docker desktop

```bash
sudo pacman -U ./docker-desktop-<version>-<arch>.pkg.tar.zst
```

5. check docker running or not

```bash
sudo systemctl status docker
```

6. if not running run this command

```bash
sudo systemctl start docker
```

</br>

**B. Command Docker**

| Command             | Description          |
| :------------------ | :------------------- |
| sudo docker version | Check version docker |

</br>

### Install bat (for cat display)

Reference : https://github.com/sharkdp/bat
A cat(1) clone with syntax highlighting and Git integration.

1. Install bat

```bash
sudo pacman -S bat
```

</br>

### Install fzf (Fuzzy Finder)

1. Install fzf with yay

```bash
yay -S fzf
```

2. run fzf

```bash
fzf
```

3. open folder with fzf

```bash
alias cdf='cd $(find * -type d | fzf)'
```

4. Custom script fzf

```bash
 vim ~/.bashrc
```

5. add script in file `.bashrc`

```bash
function cdf() {
  cd "$(find * -type d | fzf)"
}
```

6. run fzf with custom script `cdf`

</br>

### Install Audio

1. install pipewire `sudo pacman -S pipewire pipewire-pulse`
2. install pavucontrol `sudo pacman -S pavucontrol`
3. Restart computer

</br>

### Install Kdenlive

reference : https://linux-packages.com/arch-linux/package/kdenlive

1. Install kdenlive and update package

   ```cli
    sudo pacman -Sy
    sudo pacman -S kdenlive
   ```

2. Uninstall kdenlive

   ```cli
    sudo pacman -Rcns kdenlive
   ```

</br>

### Install GIMP

reference : https://archlinux.org/packages/extra/x86_64/gimp/

1. Install GIMP and update package

   ```cli
    sudo pacman -Sy
    sudo pacman -S gimp
   ```

2. Uninstall GIMP

   ```cli
    sudo pacman -Rcns gimp
   ```

</br>

### Install krita

reference : https://archlinux.org/packages/extra/x86_64/gimp/

1. Install krita and update package

   ```cli
    sudo pacman -Sy
    sudo pacman -S krita
   ```

2. Uninstall krita

   ```cli
    sudo pacman -Rcns krita
   ```

</br>

### Install Virtualbox

1. first update system

   ```bash
    sudo pacman -Syu
   ```

2. Install virtualbox with headers

   ```bash
   sudo pacman -S linux$(uname -r | grep -o -E '[0-9]+' | head -n 2 | sed 'N;s/\n//')-headers virtualbox virtualbox-host-dkms
   ```

3. Add user to group

   ```bash
   sudo usermod -aG vboxusers $USER
   ```

</br>

### Install Mysql and MySQL Workbench

Reference : https://gist.github.com/oddlyspaced/8856bd3db5132ef3714ecc40a9fe37ea

1. Updating system

   ```bash
   sudo pacman -Syyu
   ```

2. Installing software dependencies

   ```bash
   sudo pacman -S git gnome-keyring
   ```

3. Compile and Install MySQL Server, Note : (This might take like ~4 hours since it's compiling the source)

   ```bash
   git clone https://aur.archlinux.org/mysql.git
   cd mysql
   makepkg -si
   ```

4. Install MySQL-Workbench

   ```bash
   sudo pacman -S mysql-workbench
   ```

5. Setting up database

   ```bash
   sudo rm -rf /var/lib/mysql
   sudo mysqld --initialize --user=mysql --basedir=/usr --datadir=/var/lib/mysql
   # ^ Once the above command is executed successfully, make sure to copy paste the demo password displayed at screen!
   ```

6. Enabling the service

   ```bash
   sudo systemctl enable --now mysqld
   ```

7. Verifying

   ```bash
   mysql -u root -p
   # ^ Enter your dummy password from Part 5
   ```

</br>

### Install xampp and configuration

reference : https://wiki.archlinux.org/title/XAMPP

1. Download xampp for linux on website https://www.apachefriends.org/download.html

2. open file in directory `Downloads`
```bash
cd Downloads
```

3. run this command 
```bash
sudo chmod +x xampp-linux-x64-8.2.12-0-installer.run
```

4. and install xampp with 
```bash
sudo ./xampp-linux-x64-8.2.12-0-installer.run
```

5. install other package
```bash
sudo pacman -S libxcrypt-compat
sudo pacman -S net-tools
```

6. after install start xampp apache with this command
```bash
sudo /opt/lampp/lampp startapache
```

7. start mysql 
```bash
sudo /opt/lampp/lampp startmysql
```

8. example command to start,stop,restart xampp 
```bash
sudo /opt/lampp/xampp start,stop,restart
```

*note stop service apache2 if already running
```bash
sudo service apache2 stop
```

9. open localhost in browser `http://localhost/phpmyadmin/`

don't forget to add PATH xampp for run laravel project with PHP from xampp
add in your .bashrc or .bash_profile
```bash
vim .bashrc
```

copy this path

```bash
export PATH="/opt/lampp/bin:$PATH"
```
Run mysql database
```bash
/opt/lampp/bin/mysql -u root
```
</br>

### Edit file virtual host on Apache XAMPP

1. Open terminal
```bash
sudo vim /opt/lampp/etc/extra/httpd-vhosts.conf
```

2. Add config in file httpd-vhosts.conf
```bash
<VirtualHost *:80>
    DocumentRoot "/opt/lampp/htdocs/blog-website/public"
    ServerName blog-website.local
    <Directory "/opt/lampp/htdocs/blog-website/public">
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

3. Active config virtual host
```bash
sudo vim /opt/lampp/etc/httpd.conf
```
and remove sign #
```bash
Include etc/extra/httpd-vhosts.conf
```

4. Add Local Domain
```bash
sudo vim /etc/hosts
```
and add this example domain
```bash
127.0.0.1   blog-website.local
```

5. Restart Apache Server
```bash
sudo /opt/lampp/lampp restartapache
```
or
```bash
sudo /opt/lampp/lampp restart
```


</br>

### Install Composer

reference : https://getcomposer.org/download

1. Update package

```cli
# sudo pacman -Sy
```

2. install composer

```cli
# sudo pacman -S composer
```

3. check version composer

```cli
# composer -v
```

<hr>

</br>

### Change Languages Arch Linux

1. Add languages by editing `/etc/locale.gen.` Uncomment the languages you want to

```cli
#en_SG ISO-8859-1
en_US.UTF-8 UTF-8
#en_US ISO-8859-1
```

2. Run `locale-gen` to load those languages.

```cli
$ sudo locale-gen
Generating locales...
  en_US.UTF-8... done
  en_US.UTF-8... done
Genertaion complete.
```

3. Set your system language by editing `vim /etc/locale.conf.` Add `LANG=` and the language
4. Reboot

### Backup file .xinitrc manjaro-linux

```bash
#!/bin/bash
#
# ~/.xinitrc
#
# Executed by startx (run your window manager from here)

userresources=$HOME/.Xresources
usermodmap=$HOME/.Xmodmap
sysresources=/etc/X11/xinit/.Xresources
sysmodmap=/etc/X11/xinit/.Xmodmap

DEFAULT_SESSION=startplasma-x11

# merge in defaults and keymaps

if [ -f $sysresources ]; then
    xrdb -merge $sysresources
fi

if [ -f $sysmodmap ]; then
    xmodmap $sysmodmap
fi

if [ -f "$userresources" ]; then
    xrdb -merge "$userresources"
fi

if [ -f "$usermodmap" ]; then
    xmodmap "$usermodmap"
fi

# start some nice programs

if [ -d /etc/X11/xinit/xinitrc.d ] ; then
    for f in /etc/X11/xinit/xinitrc.d/?*.sh ; do
        [ -x "$f" ] && . "$f"
    done
    unset f
fi

get_session(){
    local dbus_args=(--sh-syntax --exit-with-session)
    case $1 in
        awesome) dbus_args+=(awesome) ;;
        bspwm) dbus_args+=(bspwm-session) ;;
        budgie) dbus_args+=(budgie-desktop) ;;
        cinnamon) dbus_args+=(cinnamon-session) ;;
        deepin) dbus_args+=(startdde) ;;
        enlightenment) dbus_args+=(enlightenment_start) ;;
        fluxbox) dbus_args+=(startfluxbox) ;;
        gnome) dbus_args+=(gnome-session) ;;
        i3|i3wm) dbus_args+=(i3 --shmlog-size 0) ;;
        jwm) dbus_args+=(jwm) ;;
        kde) dbus_args+=(startplasma-x11) ;;
        lxde) dbus_args+=(startlxde) ;;
        lxqt) dbus_args+=(lxqt-session) ;;
        mate) dbus_args+=(mate-session) ;;
        xfce) dbus_args+=(xfce4-session) ;;
        openbox) dbus_args+=(openbox-session) ;;
        *) dbus_args+=($DEFAULT_SESSION) ;;
    esac

    echo "dbus-launch ${dbus_args[*]}"
}

exec $(get_session "$1")

```



<hr>

</br>

# Fix Error In Arch Linux

### Fix unable to lock database

reference : https://ostechnix.com/how-to-fix-unable-to-lock-database-error-in-arch-linux/

1. Remove file db.lck
   ```cli
   sudo rm /var/lib/pacman/db.lck
   ```

2. And update again package
   ```cli
   sudo pacman -Syu
   ```


# Command terminal perhaps help me

### Set audio volume from terminal

1. Gets a list of simple mixer controls
   ```cli
    amixer scontrols 
   ```
2. and set increse audio with this example
   ```cli
    amixer sset 'Master' 100%
   ```
