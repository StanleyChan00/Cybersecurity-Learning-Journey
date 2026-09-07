# Phase 1 - Building the Network

Much of the hard work was done in [Phase 0](00-Plan-and-Structure.md) so this phase was relatively simple and just comprised of following my plan, using the intuitive GUI, and basic troubleshooting of any issues that arose.

## Getting the DC started 

I started off by building the DC. As planned, I gave it 3GB of RAM, 2 CPUs, and up to 50GB of storage using my external SSD. If any of the machines are too slow, I could always add more RAM as well. 

<img width="1888" height="862" alt="Memory and CPU" src="https://github.com/user-attachments/assets/90d73da2-766d-4ea3-bb91-227df8d7a381" />

After this, I set up the 2 network adapters according to plan. The 1st NIC connected to the NAT to give us internet access while the 2nd connected internally to form the LAN with the client machine, which I will add later on. 

The 2nd NIC will be named `ADLAN`.

<img width="1886" height="936" alt="NIC1" src="https://github.com/user-attachments/assets/3ad2bae0-e56c-400b-9c82-2e058645f93e" />


<img width="1886" height="936" alt="NIC2" src="https://github.com/user-attachments/assets/065e2f30-24e6-4d39-91e0-0159c3dcbb73" />

I also deselected the floppy disk in the boot order so it would boot up the Windows Server ISO on the Optical and then write it on the hard disk after. 

<img width="1886" height="936" alt="Boot" src="https://github.com/user-attachments/assets/d7019b22-d046-42b4-a09b-aae70a727a6e" />

I then selected the Desktop Experience OS to install so that I could have the GUI to learn optimally with.

 <img width="2276" height="1694" alt="DE" src="https://github.com/user-attachments/assets/05a3d67e-4063-4f9b-8911-15ce6378c5fb" />

After setting up a simple password, we now have the Window's Server booted up and are now ready to begin!

<img width="2068" height="1632" alt="Start" src="https://github.com/user-attachments/assets/28276434-9118-4ece-a64b-11ffccf69b41" />

### Setting Up the Network & AD Structure

First, I did an initial `ipconfig` as well as a few `ping` tests to check out the initial network as well as test our initial internet connection.

<img width="1948" height="1080" alt="Initial Network" src="https://github.com/user-attachments/assets/181901be-d33d-49f9-ae23-5e6deb5b2d64" />

Everything is already going smoothly. The internet works through the NAT from my NIC1. I was able to ping `google.com` as well as `8.8.8.8`.

However, I still had to set up the 2nd NIC, which I did here. 

<img width="2056" height="1516" alt="ADLAN DC IP Settings" src="https://github.com/user-attachments/assets/4e6f5a7e-e03d-4098-af00-00afbe359cd7" />

As planned, I used `10.10.10.10` as the static IP, a standard subnet mask, and then set the DNS server to point to itself. After setting it up and confirming it through the `ipconfig` command, I then went on to install AD DS and also changed the machine name to `DC`. 

<img width="2056" height="1516" alt="Install AD DS" src="https://github.com/user-attachments/assets/8e437672-3c4e-4f29-b05f-f6d85d5b2547" />

I then made the domain and called it `circle.lab` and restarted the machine.

 <img width="2056" height="1516" alt="Circle Login" src="https://github.com/user-attachments/assets/5beb2a08-b32e-4eda-95b4-53f0c45402ff" />

 From here, I had to set up the rest of the network so that the client could obtain an IP automatically via DHCP as well as have internet with the DC acting as the router. 

 So I installed RRAS as well as DHCP on the machine.

 <img width="2056" height="1516" alt="RRAS   DHCP" src="https://github.com/user-attachments/assets/518d2d53-8de3-4148-8d2a-a445c9244476" />

 I then set up the DHCP scope as planned.

 <img width="2056" height="1516" alt="DHCP Scope" src="https://github.com/user-attachments/assets/47e3e365-6a54-49cd-806a-38fed9ed537a" />

 To finish up the network, I went to set the DNS forwarder to google and noticed that it already automatically set my host IP as the forwarder. So I promptly removed it and set `8.8.8.8` as the forwarder instead.

<img width="2056" height="1516" alt="DNS fowarder IP host" src="https://github.com/user-attachments/assets/4d53695f-1e76-43f9-afe9-3ae413fee668" />

<img width="2056" height="1516" alt="DNS fowarder google" src="https://github.com/user-attachments/assets/96fc8800-3cfa-41aa-aa5d-ad1114f8ad5c" />

After this, the network setup has been finished! So I took a snapshot just in case.

<img width="2056" height="1516" alt="Snapshot" src="https://github.com/user-attachments/assets/57e91855-7080-454a-9fad-0e7ee60fc562" />

Lastly, the AD structure. Being able to see the GUI as well as the built-in containers is an advantage that I did not have in phase 0. 

So here, I created a new OU for the "circle" company and added all the OUs under it to distinguish from the built-in containers where everything gets dumped in. 

I created a Security Groups OU, named `groups`, which comprised of `Admins` and `Staff`.

I created a `Machines` OU, which will be where the client is. Lastly, I created the `Users` OU, which had a separate `IT` and `Staff` OU within.

I made 2 staff users named `Staff-1` and `Staff-2` as well as the main IT-Admin account, named `IT-Admin` 

<img width="2056" height="1516" alt="Staff" src="https://github.com/user-attachments/assets/5b3bc8d0-f23a-4a60-a553-6943cb610992" />

Just for simple variety of set up and experience, I made it so that the staff would have to change the password at login while the IT-admin did not. 

<img width="2056" height="1516" alt="IT-Admin" src="https://github.com/user-attachments/assets/b8f165a8-daca-4608-89b2-e75e60156e40" />

<img width="2056" height="1516" alt="Staff Creation" src="https://github.com/user-attachments/assets/8a7e7168-a5d5-42e7-ae00-8346716d00fb" />

After this, most of phase 1 is now done! We now just have to set up the Client Machine.

## Setting Up the Client Machine





 

