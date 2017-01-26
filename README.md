# termux-sudo
A bash script that provides sudo for Termux  
Termux is a terminal emulator and Linux environment for Android

**Requirements**

Rooted phone with su binary  
SUDO WILL NOT WORK WITHOUT SU

**Installing sudo**

1. Download sudo to phone and extract
2. Open Termux and change to extraction directory
3. Execute the following commands to place sudo into the correct directory with the proper permissions and ownership

```
cat sudo > /data/data/com.termux/files/usr/bin/sudo
chmod 700 /data/data/com.termux/files/usr/bin/sudo
```

**Features**

- Sets up its environment automatically on first run, no need to do anything but use it
- Takes totally zero side effect on your /system and / partition
- Creates a root folder up of the Termux home folder with proper root permissions and ownership
- Creates ```.bashrc``` file in root folder with proper PATH and LD_LIBRARY_PATH variables set so all binaries function correctly
- Bash prompt PS1 variable is also set so you don't have ```bash-4.4#``` as prompt but a better one instead
- Automatically creates ```.bash_history``` in root folder when you drop to a root shell so root shell history is preserved
- Can be used like ordinary sudo (but only as root, no other user)
- Can drop to root shell ```sudo su```
- Runs built in Termux binaries and exteral binaries with optional arguments as root in current directory
- Generates output in shell currently using
- Can be used in other bash scripts
- [option] Can turn off colored error messages be editing the variable ```colored``` at the beginning of sudo file

```
Usage:

sudo <command> [<args>]  
  Run command as root with optional arguments

sudo su | -i | --login
  Drop to root shell
```

**This was inspired by the following:**

https://github.com/cswl/tsu  
https://gist.github.com/cswl/cd13971e644dc5ced7b2  
