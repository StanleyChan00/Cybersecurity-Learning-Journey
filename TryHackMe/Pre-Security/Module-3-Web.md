# TryHackMe Pre Security - Module 3: How The Web Works
## DNS
DNS, Domain Name System, is  how website names are translated into IP addresses so that it's easy for us humans to type into a web browser and connect to.

`Google.com` for example, would be the domain name which allows us to access google through a web browser.

### Domain Hierarchy 
A domain name is structured as a hierarchy which looks like a tree, pictured below. Each section is separated by a "." and is read from right to left on the name. 

<img width="50%" height="50%" alt="Domain Hierarchy" src="https://github.com/user-attachments/assets/b26b58e1-6286-4274-87d6-0a14f8a5f27b" />

When you look up a website on a computer, the computer reads from the very right to the left of each section, asking the server of that respective section for the IP of each level. 

#### Root Domain
This is the top of the DNS hierarchy. 

All domains technically end with a "." at the end of it although hidden by web browsers and operating systems. So `Google.com` is actually `Google.com.` with an implicit "." at the end.

That "." at the end is the root domain. It doesn't contain any website data in itself. However it redirects traffic towards the Top-Level Domain(Explained below).

This root domain is needed because it lets the system know that this is the absolute end of the domain sequence and prevents the device from looking for further extensions. 
#### Top-Level Domain(TLD)
This is the `.com` or `.gov`, etc part of the domain. There are two types of TLDs. Each one is as it sounds - Generic and country.

* Generic Top Level(gTLD) : `.com`(com for Commercial), `.org`(org for organization), `.edu`(edu for education), etc. 
* Country Code Top Level Domain(ccTLD): Geographic TLDs. ex `.ca`(Canada)
#### Second-Level Domain
These are the unique website names. For example, `google.com` = "google" is the Second Level Domain.

There is a limit of only 63 characters here. Only a-z, 0-9, and hyphens can be used (Cannot start or end with a hyphen nor can it have consecutive hyphens).
#### Subdomain
From the perspective of the user visiting the website, it's kind of like visiting a separate website. 

However, it's the same domain name on the DNS server. 

It acts like a new building on a campus.

Example: `tryhackme.com` would be the regular domain name. But `admin.tryhackme.com` would be like a separate web server for admins on the tryhackme site. 

It has the same limitations of characters as the Second-Level Domain.

On top of this though. ypu can stack multiple subdomains on top of each other like `jupiter.servers.tryhackme.com`

However, the entire domain can't be more than 253 characters.

### DNS record Types

#### A Records

#### AAAA Record

#### CNAME Record

#### MX Record

#### TXT Record


### What happens when you make a request.

## HTTP in Detail

## How Websites Work

## Putting it all Together

