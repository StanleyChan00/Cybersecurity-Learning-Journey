# TryHackMe Pre Security - Module 5: Operating Systems Basics

## Operating Systems: Introduction
Operating systems(OS) are how we, as users, are able to interact seamlessly with our hardware devices.

Without an OS, it's just not feasible to do anything on most devices. It coordinates everything, from the hardware, to the applications, to us being able to see what's going on through it's user interface.

It's the middleman between the hardware on the device and us.

### System Privilege Layers
Different parts of our computer have different levels of permission in regards to access to the device. Here are the 2 main categories:

Kernel Space: This is the core part of the OS that is locked down with unrestricted access to all the physical hardware and components. Due to this, this space has absolute top privilege and restricted access.

User Space: This is everything we see and can access on our end. Any communication between this code and the hardware is restricted. It has to go through the kernel space to do so. 

### Operating System duties 
Core responsibilities of an OS include:

* Process Management - Essentially how everything is run and processed. For example, deciding which processes get CPU time and for how long(CPU scheduling) as well as starting up, pausing, and terminating applications, etc. 
* Memory Management - Manages what's on the RAM and what's not. It also isolates applications to ensure they don't interfere with each other and cause problems
* File System Management - Manages and organize files and file paths with all the metadata, etc
* User Management - Our login to the machine, accounts, permissions, authentication, etc.
* Device Management - Manages devices connected to the computer like mouses, printers, external hard drives, etc

### Operating System Security
Each OS acts as its own security foundation before any sort of external security tool(firewall, antivirus, etc) is even introduced. 

At a basic level, the OS ensures security via elements like:

* Authentication: Logins through passwords or biometrics
* Permissions: Gives certain users access to specific files or applications
* Isolation: Isolates processes to ensure each "box" is protected properly without interference like the Kernel/User Spaces.
* System Protection: Which protects the core/crucial files from unauthorized alterations

### Interfaces

Interfaces are how we interact with the OS. There are two types in which we do so.

1) **Graphical User Interface(GUI)** - This is the neat, user-friendly visual interface in which we interact with our device. All the windows, applications, and most things we visually see when looking at our monitor is the GUI.
2) **Command Line Interface(CLI)** - These are commands we enter into the terminal. Rather than everything being programmed for us to see an interact with neatly, here we interact with the OS using the command line of our OS which gives us a lot more control and precision over the system without as much limitations.

### Operating System Landscape
Each kind of device will have different uses and applications and thus a different OS depending on the job of the device that is required.

5 main types:

**1.) Desktop** - Rich and user centered GUI made for personal computers and desktops 

- Windows, MacOS, Linux, etc.

Linux is a small core kernel software and "distributions"("distros") are the Operating Systems built on top of that kernel. Like Ubuntu, Debian, Fedora

**2.) Server** - Usually no GUI and made for maximum uptime as well as remote access. 

- Windows, Linux(Ubuntu Server, Debian, CentOS, Red Hat), Unix

**3.) Mobile** - Touchscreen, network connectivity, battery efficient, etc

- Android, IOS, etc

**4.) Embedded** - Small OS made for lightweight hardware.

- OpenWrt, Ubunutu Core, Yocto Project, etc, Real-Time OS(For apps in which guaranteed response times are required like aircraft controls or braking systems, etc)


**5.) Virtual/Cloud** - OS made for data centers or cloud services. 

- Hypervisors(For data centers & Hosting or streaming services. Ubuntu LTS, Amazon Linux, Rocky Linux). Container-optimized OS(Alpine Linux, Bottlerocket AWS, Flatcar Linux)

Each type here is optimized for the function that is required of that specific device. 

## Windows Basics




## Linux CLI Basics



## Windows CLI Basics



## Operating Systems Security 
