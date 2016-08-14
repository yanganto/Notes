# Linux Shell note

---

# Package system
  * Debian, Ubuntu - deb/apt
  * RedHat, CentOS, Fedora - rpm/yum
  * SUSE - rpm/zypp
> Arch - tar.xz/pacman
---

# Common Shell

  * Bourne Shell
    * sh, ash, **bash**, dash, zsh
  * C Shell
    * csh, **tcsh**
> Zsh is the best shell
  
---

# Boot Sequence
boot loader -> kernel(/boot/vmlinuz) -> /sbin/init (define run level)
->
* /etc/rc.d/rc.sysin
* /etc/rc.d/rcN.d/*
* /etc/rc.d/rc.local
* mingetty -> /bin/login(/etc/password)
---

# Pipeline & Redirect 
- 0: Standard Input (STDIN) 
- 1: Standard Output (STDOUT) 
- 2: Standard Error Output (STDERR) 

`$ program1 | program2` # pile command1 stdout to program2 stdin 

`$ command > file.txt` # redirect stdout to file.txt  
`$ command >> file.txt` # redirect stdout and append to file.txt  
`$ command 2> error.login` # redirect stderr to error.log  

`$ command &> all.log` # redirect stdout and stderr to all.log  
`$ command > all.log 2>&1` # redirect stdout and stderr to all.log  
> 2>&1 direct stderr into stdout   
> 1>&2 and >&2 direct stdout into stderr 

---

# Another Pipe

```
$ tr a-z A-Z << END_STRING
> one two three
> hello 
> END_STRING
```
ONE TWO THREE  
HELLO

---

# Command Substitution
```
$ rm `cat filelist.txt`	# remove files written in filelist

$ current_folder=`pwd`	# pwd get the current folder and assign to
$ echo $current_folder	# $current_folder variable

$ vi note-`date +%F`.txt	# vi note-2013-05-04.txt
```

---

# Network Command

```
# ifconfig  
# ifconfig <interface> 192.168.1.2 netmask 255.255.255.0 
```
> This setting is only in memory

```
# route 
# route add default gw 192.168.1.200
# route del default gw 192.168.1.200
```

```
# ifconfig <interface> up 
# ifconfig <interface> down 
```

