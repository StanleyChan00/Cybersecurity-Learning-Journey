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

* **Laptops:** Portable computers with battery
* **Desktop:** Stationary computer that's typically stronger and can use the extra space for bigger and better components
* **Workstation:** High performance "desktop" meant for professional work 
* **Server:** Usually no monitors but serve to handle network requests and hosting 
* **Smartphone:** Our mobile "computers" that fit in our pocket
* **Tablet:** Larger screen "smartphone" 
* **IoT devices:** Devices connected to networks with a single purpose like thermostats, smart doorbells, fitness tracking watches, etc
* **Embedded Computers:** "Computers" built into another device like a coffee maker controller, automatic door sensor, lamp dimmer chips, etc

The difference between IoT and Embedded Computers is mainly that IoT devices are connected to networks. 

## Client-Server Basics
This lesson gives an overview of the previous Module 3 - "How websites work", which I covered all in depth.

However here, it gives us a nice analogy of ordering pizza as a visual in how interacting with a web server works:

<img width="1109" height="749" alt="Visual" src="https://github.com/user-attachments/assets/bfbca077-c47f-48c0-93de-dec4c8906e59" />

In essence:

1) Alice wants to order Pizza and sends Bob to the Pizza shop.
2) Bob uses the "DNS" to find the "Address"("IP address") of the shop.
3) He chooses which "port" to enter through if he wants to get takeout, delivery, etc.
4) When ordering the pizza at the register, him and the cashier use a "protocol" which is how they communicate
5) Bob "requests" and the "server" responds back and Bob brings the pizza back to Alice.

In technical terms, Alice is the client. She uses her web browser to connect to a web server. In order to do so, she uses the DNS to find the IP address of the website she wants to access along with the corresponding port. 

She communicates with the web server using the HTTP protocol, by making an HTTP request and the server responding with their HTTP response. Then Alice's browser converts the code/data sent from the server into the visual readable data - ie. the website. 

### HTTP Commands

In addition to the commands explored in Module 3, this lesson gives us a few more examples:

* Patch - Partially Modifies a resource (like updating an email address without changin anything else like their name/password)
* Head - Just a `GET` request, except it only asks for the headers and not the body. It only asks for the metadata.
* Options - Asks the server what HTTP commands are allowed on that server
* Connect - Sets up a secure connection between the two devices without any intermediates that can see it. For example, when connecting to a web server while I'm at school using the school wifi, we can use this command to create a proxy connection which prevents the school from seeing our data sent through the website server.
* Trace - Kind of like a diagnostic test. It sends a request to the server, in which the server echoes it back in the exact same way so we can see if anything between them altered the request

(Quick note. Most web servers disable the `TRACE` request method due an attack called "Cross-Site Tracking(XST) which could force the browser to "echo" back hidden secure session cookies or more.)

This lesson allowed us to use their virtual machine to see these commands in real time. It looks like this:

<img width="1219" height="912" alt="Lab" src="https://github.com/user-attachments/assets/f0cbe7a0-801a-440c-b682-8c85ef89c1d6" />

All the GET request methods we sent as well as the headers are there. We could also see the response the server sent back as well as the response's body on a separate tab.


## Virtualisation Basics


## Cloud Computing Fundamentals

