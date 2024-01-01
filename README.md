# my-archlinux-setting

### Reference
https://github.com/prasanthrangan/hyprdots

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
