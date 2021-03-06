Install UCB CHISEL on Windows 10 in easy way
===

### Setup Environment
* Operation System: Windows 10
* Required Windows Feature: **Bash on Ubuntu on Windows**
* 1. Ubuntu 14.04 LTS (Windows Anniversary Update, 2016)
* 2. Ubuntu 16.04 LTS (Windows Creator Update, 2017, Recommendation) 

> Comment(Version):  
> For Start Menu Bash ICON and better bash console interface, I'm highly recommend update Windows to Creator Update. 

![startMenu](https://raw.githubusercontent.com/wats0n/install-chisel-win10/master/images/startMenuBashIcon.png)

> Comment(Quota):  
> Please, preserve lots of free space on C disk for Ubuntu installation and setup packages. Because no options for Ubuntu installer (lxrun.exe) to change installation directory.

### Install Steps
1. Install Bash on Ubuntu on Windows [14.04_RefLink](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/) [16.04_RefLink](https://blogs.msdn.microsoft.com/commandline/2017/04/11/windows-10-creators-update-whats-new-in-bashwsl-windows-console/)
    * Manual update Ubuntu by following commands in order:
    > ```bash
    > #Require password if not login as root 
    > sudo apt-get update #update package information
    > sudo apt-get upgrade #update packages
    > sudo apt-get dist-upgrade #update ubuntu system
    > ```
    * User Home Folder path in Windows and Ubuntu [RefLink](http://askubuntu.com/questions/759880/where-is-the-ubuntu-file-system-root-directory-in-windows-nt-subsystem-and-vice)
    * File System for Windows Subsystem  for Linux [RefLink](https://blogs.msdn.microsoft.com/wsl/2017/04/18/file-system-improvements-to-the-windows-subsystem-for-linux/)
    * [Ubuntu 14.04 LTS] Remove `sudo: unable to resovle host` message [RefLink](http://askubuntu.com/questions/59458/error-message-when-i-run-sudo-unable-to-resolve-host-none)
	* [Ubuntu 14.04 LTS] Example: Edit `/etc/hosts` on my computer
	> ![localhost](https://raw.githubusercontent.com/wats0n/install-chisel-win10/master/images/addLocalHost.PNG)
2. Setup Initialization Script for login directory
    * Default is Windows system32 directory (where we invoke bash.exe), please don't do `sudo rm -rf` in system32 directory.
    * Add `cd ~/` or your project directory into `~/.bashrc` at last line.
3. Following Chisel (Ubuntu-like) Linux Installation [RefLink](https://github.com/ucb-bar/chisel3/)
	* In this Example, working directory is `D:\CompArch\Projects\`, transformed identical path in Ubuntu bash is `/mnt/d/CompArch/Projects/`
	* If you want to save bash commands into bash script, please change line endings in editor.
	> ![script](https://raw.githubusercontent.com/wats0n/install-chisel-win10/master/images/buildScript.png)
	* Install Verilator is normally complete.
	> ![verilator](https://raw.githubusercontent.com/wats0n/install-chisel-win10/master/images/installVerilatorOnWin10.PNG)
4. Run the Chisel tutorial [RefLink](https://github.com/ucb-bar/chisel-tutorial)
	* Build tutorial by Scala Build Tool
	> ![init](https://raw.githubusercontent.com/wats0n/install-chisel-win10/master/images/initChiselTutorial.PNG)
	* After long time to build Scala environment.
	> ![finish](https://raw.githubusercontent.com/wats0n/install-chisel-win10/master/images/finiChiselTutorial.PNG)
5. Happy Hardware Hacking!

### Issues
1. [Ubuntu 14.04 LTS] Java version Problem
    * If Ubuntu has installed Java9(OpenJDK-9), the CHISEL resource would fetch failure on .jar resources.
    * Solution: Install OpenJDK-8 on Ubuntu 14.04LTS [RefLink](http://askubuntu.com/questions/464755/how-to-install-openjdk-8-on-14-04-lts/666481#666481)
    * Please check the java/javac is OpenJDK-8 for Chisel library. By following commands:
        > `sudo update-alternatives --config java`
        > `sudo update-alternatives --config javac`
    > ![finish](https://raw.githubusercontent.com/wats0n/install-chisel-win10/master/images/updateJava8Version.PNG)
2. [Ubuntu 14.04 LTS] Symbolic Link has recursive list file problem in current bash on windows, please change to native support directory `/mnt/(logic disk in Windows Explorer)/`. [Ubuntu 14.04 LTS]
    * Symbolic Link Directory [RefLink](http://stackoverflow.com/questions/9587445/how-to-create-a-link-to-a-directory)
    * Remove Symbolic Link [RefLink](http://askubuntu.com/questions/398818/how-to-remove-symbolic-link)
    