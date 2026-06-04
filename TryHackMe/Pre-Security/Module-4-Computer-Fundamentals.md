# TryHackMe Pre Security - Module 4: Computer Fundamentals
## Inside a Computer System

**Motherboard:** This is what connects all components together and allows them to communicate. Everything plugs into or connects through the motherboard.

**Central Processing Unit(CPU):** The "brain" of the computer which performs all the calculations and executes all the instructions

**Random Access Memory(RAM):** This is the "short term memory" of the computer which allows for us to get fast access to the data within. It's temporary and volatile as the content within disappears when power is gone.

**Storage(SSD/HDD - Solid State Drive/Hard Disk Drive):** This is the storage for long term data. SSD is fast but more expensive and has no moving parts(safer). HDD is cheaper but has moving parts and is thus prone to failure. 

**Power Supply(PSU):** Powers the entire device

**Graphics Card(GPU - Graphic Processing Unit):** Proceesses and outputs visual data to monitors/displays

**Input/Output(I/O)** devices: Keyboards, flashdrives, monitors, etc.

It looks like this on the motherboard:

<img width="1164" height="764" alt="Motherboard" src="https://github.com/user-attachments/assets/fa111a6f-fa8f-441c-861f-7d2ef450a5c9" />

### What Happens When You Press the Start Button

Here's all the steps our computer goes through when we first power on the device and before it's operating system boots up:

<img width="796" height="95" alt="Start Button" src="https://github.com/user-attachments/assets/62910035-19a6-4685-a9d0-3fed103a3ce2" />

1) The power button sends a signal to the PSU to begin powering up the whole system. Now, electricity starts flowing through the device.
2) This is where the firmware, which gets all the components in our device to start up, gets booted up. The main firmware currently used is "Unified Extensible Firmware Interface"(UEFI). UEFI has mostly replaced "BIOS", which was used in the past.
3) "Power On Self Test"(POST) is one of the routines UEFI uses to ensure everything is present and functioning correctly
4) This is where UEFI looks for where the bootloader program(Explained in the next step) is stored on the device. The UEFI has a priority list(the "boot order") which it looks through sequentially to find them.
5) The UEFI executes a small "bootloader" program stored on the device, which knows where the Operating System is and takes that OS and copies it onto the RAM. At this point, the OS now takes full control over the computer

## Computer Types


## Client-Server Basics


## Virtualisation Basics


## Cloud Computing Fundamentals

