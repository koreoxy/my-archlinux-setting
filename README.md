# My Arch Linux Setting

## My Setup Image
![my-arch-linux-setup](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/3e3bb5f5-b208-4d75-b85a-de5f2c828831)


## Jump to
- [Command Arch Linux](#command-arch-linux)
- [Install Arch Linux](#install-arch-linux)
- [Post Install Arch Linux](#post-install-arch-linux)


## Command Arch Linux
|      Command                                    |                     Description                               | 
| :-----                                         |                          :---                              |  
| xrandr                                          |      Check list resolution monitor             |  
| xrandr --output "Virtual-1" --mode 1920x1080   |      Change resolution monitor             |  




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
# mdkir suckless
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
- Toggle forward and backward between window viewing  FORWARD = `ALT + J`, BACKWARD = `ALT + K`
- Close Window on active `ALT + SHIFT + c`
- Run program with dmenu `ALT + p`
- Move workspace `ALT + 1 2 3 4`
- Move window to different workspace `ALT + SHIFT + 1 2 3 4`
- move space window to left `ALT + h`, right `ALT + l`
- Move window to down `ALT + d` to left `ALT + i`
- Change mode window to float `ALT + SPACE`
- hide top bar dmenu `ALT + B`
- zoom in and zoom out in terminal `CTRL + SHIFT PgUp` and `CTRL + SHIFT + pgDn`

<hr>

</br>


### Patching dwm
1. Download patches : https://dwm.suckless.org/patches/
2. create folder in `suckless/dwm/patches`
3. copy file config `cp config.h config.def.h`
4. install patch `patch -i patches/dwm-name-version.diff`
5. after isntall patch `sudo make clean install` on folder dwm



<hr>

</br>

### File .xinitrc
```cli
~/.fehbg &
xrandr --output "Virtual-1" --mode 1280x720 &
picom &
slstatus &

#exec startplasma-x11
exec dwm

```



<hr>

</br>


### Set wallpaper
see general command `man feh`
1. install feh `sudo pacman -S feh`
2. set wallpaper `feh --bg-scale Pictures/name-wallpaper`


<hr>

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



<hr>

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

## Install Audio
1. install pipewire `sudo pacman -S pipewire pipewire-pulse`
2. install pavucontrol `sudo pacman -S pavucontrol`
3. Restart computer

</br>


## Install xampp and configuration
reference : https://wiki.archlinux.org/title/XAMPP

1. Download xampp for linux on website https://www.apachefriends.org/download.html
2. open file in directory `Downloads`
3. run this command `# sudo chmod +x xampp-linux-x64-8.2.12-0-installer.run`
4. and install xampp with `# ./xampp-linux-x64-8.2.12-0-installer.run`
5. install other package `# sudo pacman -S libxcrypt-compat` and `# sudo pacman -S net-tools`
6. after install start xampp apache with this command `# /opt/lampp/lampp startapache`
7. start mysql `# /opt/lampp/lampp startmysql`
8. example command to start,stop,restart xampp `# /opt/lampp/xampp start,stop,restart`
9. open localhost in browser `http://localhost/phpmyadmin/`

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

## Change Languages Arch Linux
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
