Install Chisel on Windows 10 in easy way
===
### Setup Environment
Operation System: Windows 10
Required Windows Feature: **Bash on Ubuntu on Windows** (Ubuntu 14.04 LTS)
Comment: Please, preserve lots of free space on C disk for Ubuntu installation and setup packages. Because no options for Ubuntu installer (lxrun.exe) to change installation directory.
### Install Steps
1. Install Bash on Ubuntu on Windows [RefLink](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/)
    > Manual update by following commands in order:
    > ```bash
    > #Require password if not logging as root 
    > sudo apt-get update #update package information
    > sudo apt-get upgrade #update packages
    > sudo apt-get dist-upgrade #update ubuntu system
    > ```
    > File System hierarchy [RefLink](http://askubuntu.com/questions/759880/where-is-the-ubuntu-file-system-root-directory-in-windows-nt-subsystem-and-vice)
    > Remove `sudo: unable to resovle host` [RefLink](http://askubuntu.com/questions/59458/error-message-when-i-run-sudo-unable-to-resolve-host-none)
2. Setup Initialization Script for login directory
    > Default is Windows system32 directory (where we invoke bash.exe), please don't do `sudo rm -rf` in system32 directory.
    > Add `cd ~/` or your project directory into `~/.bashrc` at last line.
3. Following Chisel (Ubuntu-like) Linux Installation [RefLink](https://github.com/ucb-bar/chisel3/)
4. Run the Chisel tutorial [RefLink](https://github.com/ucb-bar/chisel-tutorial)
5. Happy Hacking!

### Issues
1. Symbolic Link has recursive list file problem in current bash on windows, please change to native support directory `/mnt/(logic disk in Windows Explorer)/`.
    > Symbolic Link Directory [RefLink](http://stackoverflow.com/questions/9587445/how-to-create-a-link-to-a-directory)
    > Remove Symbolic Link [RefLink](http://askubuntu.com/questions/398818/how-to-remove-symbolic-link)
    > 
