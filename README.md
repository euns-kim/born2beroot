# Born2beroot

## What is a virtual machine?

"A virtual machine (VM) is a virtual environment that works like a computer within a computer. It runs on an isolated partition of its host computer with its own CPU power, memory, operating system (such as Windows, Linux, macOS), and other resources. End users can run applications on VMs and use them as they normally would on their workstation."

### How do virtual machines work?

"Virtual machines are made possible through virtualization technology. Virtualization uses software to simulate virtual hardware that allows multiple VMs to run on a single machine. The physical machine is know as the host while the VMs running on it are called guests.

This process is managed by software known as hypervisor. The hypervisor is responsible for managing and provisioning resources – like memory and storage – from the host to guests. It also schedules operations in VMs so they don't overrun each other when using resources."

Type 1 hypervisors (bare metal hypervisors) are installed natively on the underlying physical hardware. Host machines running type 1 hypervisors are used only for virtualization. They're often found in server-based environments like enterprise data centers.

Type 2 hypervisors (hosted hypervisors) run on the host computer's operating system. Unlike bare-metal hypervisors, guest operating systems are not tied to physical hardware. Users can run VMs and use their computer systems as usual. This makes type 2 hypervisors suitable for personal users or small businesses that don't have dedicated servers for virtualization.

### virtual desktop infrastructure (VDI)

VDI deployments allow users to remotely access desktop environments, such as Windows or open source operating systems like Linux.

### benefits of using virtual machine

1) It enhances security – VM environments are isolated from the host operating system and can be easily reverted to older versions.

2) It improves cost efficiency – by hosting multiple VMs on one server, the physical hardware is leveraged at its maximum capacity.

3) Cloud computing

4) Scalability

source: https://www.citrix.com/solutions/vdi-and-daas/what-is-a-virtual-machine.html


## What is "root" on Linux?

The root user is the Linux superuser. The root account should be used exclusively for administrative purposes.

### sudo command

The sudo command makes it possible to administer Linux computers without logging in as the root user. It bestows root's authority only to those, who are added to the sudoers list.

