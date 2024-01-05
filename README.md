# my-archlinux-setting

### Reference
https://github.com/prasanthrangan/hyprdots

</br>

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
![VirtualBoxVM_uCfvdjegzd](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/0247935f-c055-4170-9e88-4c31da1d813b)
![bPtMg06mBr](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/60c4b0c2-ebf1-421e-b9a3-a32f356ef796)

- Aditional Package :
  ![M72VmRaGBI](https://github.com/koreoxy/my-archlinux-setting/assets/73381115/86e07e4c-c963-4680-9b20-aa21739a9e91)





</br>

### Install xampp and configuration
reference : https://wiki.archlinux.org/title/XAMPP

1. Download xampp for linux on website https://www.apachefriends.org/download.html
2. open file in directory `Downloads`
3. run this command `# sudo chmod +x xampp-linux-x64-8.2.12-0-installer.run`
4. and install xampp with `# ./xampp-linux-x64-8.2.12-0-installer.run`
5. install other package `# sudo pacman -S libxcrypt-compat` and `# sudo pacman -S net-tools`
6. after install start xampp apache with this command `# /opt/lampp/lampp startapache`
7. start mysql `# /opt/lampp/lampp startmysql`
8. example command to start,stop,restart xampp `# /opt/lampp/xampp start,stop,restart`

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
