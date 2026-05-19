


# TryHackMe Pre Security - Module 2: Network Fundamentals

## What is Networking?
A network isn't necessarily exclusive to devices and computers. Anything connected together can form a network, such as a public transportation system or a network of friends within a neighborhood.

A network, in the context of cybersecurity, is simply a group of devices connected to each other. The internet is what connects private networks together.

**Internet Protocol(IP) Address:** An identifying number assigned to a device on a network. A public address (given by the Internet Service Provider (ISP)) identifies that network on the wider global internet, while a private address identifies a specific device within a local network.

Example IP address: `192.168.1.1`

Each section of the IP address is known as an octet. IPv4 is currently the main numbering protocol being used. IPv6 is the newer protocol, which allows for a  larger number of IP addresses.

**Media Access Control(MAC) Address:** This is the unique physical identifier that comes with each device and can not be changed.

Example MAC address: `a4:c3:f0:85:ac:2d`

An example of an attack is called "spoofing" which is a malicious attacker pretending to have a different MAC address to gain access into a poorly made system. 

**Ping:** `ping` is the command used to test the connection between devices. It does this by sending Internet Control Message Protocol(ICMP) packets to a device and tests the time for it to go to the device and back. 

The syntax is just: `ping "(IP Address/URL)"`

## Intro to LAN
### Local Area Network(LAN) Topologies:
The architecture of a network.

#### Star Topology:

Center networking device which has all the devices connect individually to it

#### Bus Topology:

Visually speaking, it’s just a tree branch that has further branches that stem from that singular branch.

All the data travels through the same branching cable.

#### Ring Topology:

All the devices are connected to each other in a form of a loop. Data can only travel in one direction through each device, like a circle.

#### Switch:

Rather than indiscriminately sending data out to everyone, a switch is a device which allows you to discriminately decide which device will get the data. 

Like a mailman handing out mail that was designated for a single house. 

#### Router:

A router connects networks together. A home router, for example, connects that private local area network(LAN) to the public wide area network(WAN/Internet).

### Subnetting:

This is the process of splitting up a network into smaller individually separated networks.

This is done through **subnet masks**. 

Converting to binary:

To understand this, we need to understand that IP addresses are not just numbers but in computer terms, bits. Specifically, 32 bits long.**(Note, this isn’t in this module of the course but I wanted to ensure I understood this)**

Example: IP address:

`192.168.1.10` is actually `11000000.10101000.00000001.000010101`

This conversion happens within each octet and each octet has 8 values. Whenever one byte is flipped “on” as “1”, that value will get added with the rest of the other bytes that are also flipped “1”

The positional values within an octet are as follows:

`128, 64, 32, 16, 8, 4 , 2 , 1` so with our example, the 2nd octet of our IP address, 10101000, will be:

`128 + 0 + 32 + 0 + 8 + 0 + 0 + 0 = 168`

Hence how we get the second octet of our example IP 192.**168**.1.10

#### Subnet Masks:
This is essentially how we both translate an IP address to see which network it is on as well as how we define the subnets

Subnet masks look just like an IP address and are also 32 bits long. The difference here is that they **always** have consecutive 1s followed by consecutive 0s. 

It looks like this for example: `255.255.255.0` or in binary `11111111.11111111.11111111.00000000`

You line this up with the IP address of a device. Each "1" that the IP address lines up with in regards to the subnet mask represents the network address. To illustrate:

`11000000.10101000.00000001.000010101` - IP address: `192.168.1.10`

`11111111.11111111.11111111.00000000` - Subnet Mask: `255.255.255.0` 

Every time the 1 appears, we just carry it down from that same position within the IP address. By doing so, we get:

`11000000.10101000.00000001.00000000` - Network address: `192.168.1.0`

(Just to note that `/24`, for example is a notation used to express the amount of "1s" in the subnet mask)

**Subnetting:** In regards to the example above, the entire last octet is available for use. That means that there is a maximum of 256 devices/IP address that can be used on that network.

Now, say we want to division out this network and have 2 seperate subnets instead. To do this, we just "borrow" a bit from the subnet mask. So now the subnet mask would be:

`11111111.11111111.11111111.10000000` - Subnet Mask: `255.255.255.128` 

By doing this, the network was effectively cut in half. It went from one network with 256 devices to two networks with 128 devices each. 


## OSI Model

## Packets & Frames

## Extending Your Network
