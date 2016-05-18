# Linux Shell programing note

Package system
===
  * Debian, Ubuntu - deb/apt
  * RedHat, CentOS, Fedora - rpm/yum
  * SUSE - rpm/zypp
> Arch - tar.xz/pacman

Common Shell
===
  * Bourne Shell
    * sh, ash, **bash**, dash, zsh
  * C Shell
    * csh, **tcsh**
> Zsh is the best shell
  
Boot Sequence
===
boot loader -> kernel(/boot/vmlinuz) -> /sbin/init (define run level)
->
* /etc/rc.d/rc.sysin
* /etc/rc.d/rcN.d/*
* /etc/rc.d/rc.local
* mingetty -> /bin/login(/etc/password)
