# TryHackMe Pre Security - Module 5: Operating Systems Basics

## Operating Systems: Introduction
Operating systems(OS) are how we, as users, are able to interact seamlessly with our hardware devices.

Without an OS, it's just not feasible to do anything on most devices. It coordinates everything, from the hardware, to the applications, to us being able to see what's going on through it's user interface.

It's the middleman between the hardware on the device and us.

### System Privilege Layers
Different parts of our computer have different levels of permission in regards to access to the device. Here are the 2 main categories:

Kernel Space: This is the core part of the OS that is locked down with unrestricted access to all the physical hardware and components. Due to this, this space has absolute top privilege and restricted access.

User Space: This is everything we see and can access on our end. Any communication between this code and the hardware is restricted. It has to go through the kernel space to do so. 

### OS duties 
Core responsibilities of an OS include:

* Process Management - Essentially how everything is run and processed. For example, deciding which processes get CPU time and for how long(CPU scheduling) as well as starting up, pausing, and terminating applications, etc. 
* Memory Management - Manages what's on the RAM and what's not. It also isolates applications to ensure they don't interfere with each other and cause problems
* File System Management - Manages and organize files and file paths with all the metadata, etc
* User Management - Our login to the machine, accounts, permissions, authentication, etc.
* Device Management - Manages devices connected to the computer like mouses, printers, external hard drives, etc

### OS Security
Each OS acts as its own security foundation before any sort of external security tool(firewall, antivirus, etc) is even introduced. 

At a basic level, the OS ensures security via elements like:

* Authentication: Logins through passwords or biometrics
* Permissions: Gives certain users access to specific files or applications
* Isolation: Isolates processes to ensure each "box" is protected properly without interference like the Kernel/User Spaces.
* System Protection: Which protects the core/crucial files from unauthorized alterations 


## Windows Basics




## Linux CLI Basics



## Windows CLI Basics



## Operating Systems Security 
