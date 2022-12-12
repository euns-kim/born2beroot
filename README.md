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

source:
- https://www.citrix.com/solutions/vdi-and-daas/what-is-a-virtual-machine.html


## Linux basics

### 1) What is "root" on Linux?

The root user is the Linux superuser. The root account should be used exclusively for administrative purposes. If there is only one user, the user automatically has the root authority.

### 2) /etc/shadow

The "/etc/shadow" file contains the username of each account on the Linux computer, along with other pieces of information, including each account's encrypted password, when the password was last changed, and when the password expires. It can only be read by root.

### 3) sudo command

The sudo command makes it possible to administer Linux computers without logging in as the root user. It bestows root's authority only to those, who are added to the sudoers list.

#### 3-1) sudo vs su

Sudo authentification is through user's own password, whereas su authentification through the root user's password. You first need to assign a password to the root user and everyone has to know the root user's password to use su – it risks the system security. It is much more secure to the sudoers list and sudo than su for that reason.

#### 3-2) sudo bash

Using sudo to run a Bash shell opens a new shell with root as the user, so that one does not need to type 'sudo' repeatedly. To exit from the root user's shell, hit 'ctrl+D' or type 'exit' and hit enter.

#### 3-3) /etc/sudoers

The "etc/sudoers" file MUST be edited with the 'visudo' command as root. The authority to rewrite sudoers is not given to anyone including the root.

### 4) Secure Path

The shell PATH that is used to execute sudo.

#### 4-1) How does PATH work in Bash?

The PATH variable is responsible for telling bash where to look for programmes that certain commands are calling. In other words, the PATH variable stores where executables may be found. Whenever any command is run, the shell looks up the PATH directories for the target executable file and runs it. Most of the command tools are located under the /usr/bin directory.

#### 4-2) echo $PATH

The $ sign is to denote a variable. The echo command prints the value of the PATH variable. Each of the directories is separated by a ':' sign.

source:
- https://www.howtogeek.com/737563/what-is-root-on-linux/
- https://www.tuwlab.com/ece/24044
- https://linuxhint.com/path_in_bash/