# my-archlinux-setting


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
