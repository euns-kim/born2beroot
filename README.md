# Born2beroot

## What is a virtual machine?

"A virtual machine (VM) is a virtual environment that works like a computer within a computer. It runs on an isolated partition of its host computer with its own CPU power, memory, operating system (such as Windows, Linux, macOS), and other resources. End users can run applications on VMs and use them as they normally would on their workstation."

### How do virtual machines work?

"Virtual machines are made possible through virtualization technology. Virtualization uses software to simulate virtual hardware that allows multiple VMs to run on a single machine. The physical machine is know as the host while the VMs running on it are called guests.

This process is managed by software known as hypervisor. The hypervisor is responsible for managing and provisioning resources – like memory and storage – from the host to guests. It also schedules operations in VMs so they don't overrun each other when using resources."

Type 1 hypervisors (bare metal hypervisors) are installed natively on the underlying physical hardware. Host machines running type 1 hypervisors are used only for virtualization. They're often found in server-based environments like enterprise data centers.

Type 2 hypervisors (hosted hypervisors) run on the host computer's operating system. Unlike bare-metal hypervisors, guest operating systems are not tied to physical hardware. Users can run VMs and use their computer systems as usual. This makes type 2 hypervisors suitable for personal users or small businesses that don't have dedicated servers for virtualization.

### Virtual Desktop Infrastructure (VDI)

VDI deployments allow users to remotely access desktop environments, such as Windows or open source operating systems like Linux.

### Benefits of using virtual machine

1) It enhances security – VM environments are isolated from the host operating system and can be easily reverted to older versions.
2) It improves cost efficiency – by hosting multiple VMs on one server, the physical hardware is leveraged at its maximum capacity.
3) Cloud computing
4) Scalability

Source:
- https://www.citrix.com/solutions/vdi-and-daas/what-is-a-virtual-machine.html


## Linux basics

### 1)	What is "root" on Linux?

The root user is the Linux superuser. The root account should be used exclusively for administrative purposes. If there is only one user, the user automatically has the root authority.

### 2)	/etc/shadow

The "/etc/shadow" file contains the username of each account on the Linux computer, along with other pieces of information, including each account's encrypted password, when the password was last changed, and when the password expires. It can only be read by root.

### 3)	sudo command

The sudo command makes it possible to administer Linux computers without logging in as the root user. It bestows root's authority only to those, who are added to the sudoers list.

#### 3-1)	sudo vs su

Sudo authentification is through user's own password, whereas su authentification through the root user's password. You first need to assign a password to the root user and everyone has to know the root user's password to use su – it risks the system security. It is much more secure to the sudoers list and sudo than su for that reason.

#### 3-2)	sudo bash

Using sudo to run a Bash shell opens a new shell with root as the user, so that one does not need to type 'sudo' repeatedly. To exit from the root user's shell, hit 'ctrl+D' or type 'exit' and hit enter.

#### 3-3)	/etc/sudoers

The "etc/sudoers" file MUST be edited with the 'visudo' command as root. The authority to rewrite sudoers is not given to anyone including the root.

### 4)	Secure Path

The shell PATH that is used to execute sudo.

#### 4-1)	How does PATH work in Bash?

The PATH variable is responsible for telling bash where to look for programmes that certain commands are calling. In other words, the PATH variable stores where executables may be found. Whenever any command is run, the shell looks up the PATH directories for the target executable file and runs it. Most of the command tools are located under the /usr/bin directory.

#### 4-2)	echo $PATH

The $ sign is to denote a variable. The echo command prints the value of the PATH variable. Each of the directories is separated by a ':' sign.

### 5)	apt command

APT stands for Advanced Package Tool. It is a set of core tools inside Debian and Ubuntu Linux system. You can use the apt command to install, delete or remove apps, keep Ubuntu/Debian server up to date with security patches and more.

`sudo apt update`  
`sudo apt upgrade`  
`apt list`	(list all packages)  
`apt list --upgradable`  
`apt list --installed`  
`apt depends [pkg_name]`	(list all the dependencies a package has)  
`sudo apt install [pkg_name]`  
`sudo apt remove [pkg_name]`  
`sudo apt purge [pkg_name]`	(remove both package and config files)  
`sudo apt (--purge) autoremove`	(remove automatically installed packages when no longer needed)  
`apt search [pkg_name]`  
`apt show [pkg_name]`	(show information about the given package(s))  
`apt rdepends [pkg_name]`	(recursive dependency listings similar to apt-cache)  
`sudo apt-mark hold [pkg_name]`	(Package holding means it can be upgraded till you run unhold on it again.)  
`sudo apt-mark unhold [pkg_name]`  
`sudo apt edit-sources`	(edit the source information file)  

### 6)	dpkg command

`dpkg` is a package manager for Debian, Ubuntu and many other Linux distro.

`dpkg -l`	(list all installed packages, along with package version and short description)  
`dpkg -l [pkg_name]`	(list individual installed packages)  
`dpkg -l | grep [pkg_name]`	(check if a programm is successfully installed)  

### 7)	getent command

The `getent` command displays entries from databases supported by the Name Service Switch libraries, which are configured in /etc/nsswitch.conf.

### 8) grep command

The `grep` command searches for the pattern specified by the Pattern parameter and writes each matching line to standard output. 

`grep [option][pattern][filename]`

### 9) How to list users in Linux

`cat /etc/password`  
`getent passwd`  

- Username
- Encrypted password (`x` means that the password is stored in the file)
- User ID number (UID)
- User's group ID number (GID)
- Full name of the user (GECOS)
- User home directory
- Login shell (defaults to `/bin/bash`)

`awk -F: '{ print $1}' /etx/passwd`  
`cut -d: -f1 /etc/passwd`  
`getent passwd | awk -F: { print $1}`
`getent passwd | cut -d: -f1`

- only the usernames

getent passwd | grep [username]

- check if the user exists

getent passwd | wc -l

- check how many user accounts are on the system

Source:
- https://www.howtogeek.com/737563/what-is-root-on-linux/
- https://www.tuwlab.com/ece/24044
- https://linuxhint.com/path_in_bash/
- https://www.cyberciti.biz/faq/ubuntu-lts-debian-linux-apt-command-examples/
- https://www.cyberciti.biz/howto/question/linux/dpkg-cheat-sheet.php?utm_source=Linux_Unix_Command&utm_medium=faq&utm_campaign=nixcmd
- https://man7.org/linux/man-pages/man1/getent.1.html
- https://coding-factory.tistory.com/802
- https://coding-factory.tistory.com/803
- https://linuxize.com/post/how-to-list-users-in-linux/




## Project related commands

1. group and user

+ Create a group:  

`sudo groupadd [group_name]`  

+ Check if a group created:  

`getent group`

+ Check all local users:  

`cut -d: -f1 /etc/passwd`  

+ Create a user:  

`sudo adduser [new_username]`  

+ Assign an user into a group:  

`sudo usermod -aG [group_name] [username`]`  

+ Check which users are in a group:  

`getent group [group_name]`  

+ Check which groups user account belongs:  

`groups`  

+ Check password rules for the user:  

`chage -l [new_username]`  

2. hostname

+ Check current hostname:  

`hostnamectl`  

+ Change the hostname:  

`hostnamectl set-hostname [new_hostname]`  

+ Change /etc/hosts file:  

`sudo nano /etc/hosts`  

+ Change old_hostname with new_hostname:  

```
127.0.0.1	localhost  
127.0.0.1	new_hostname  
```

+ Reboot:

`sudo reboot`

3. sudo

+ Adding user to sudo group:  

`adduser [user_name] sudo`  

+ Alternatively:  

`usermod -aG sudo [user_name]`  

+ Verify:  

`getent group sudo`  


# What is TTY?
# CentOS vs Debian
# SELinux or Apparmor
# aptitude vs apt