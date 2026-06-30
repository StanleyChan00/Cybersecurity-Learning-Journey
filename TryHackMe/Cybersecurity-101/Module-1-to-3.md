# Module 1 - Start Your Cybersecurity Journey

## Search Skills

### Shodan

[Shodan](https://www.shodan.io/) is really good scanning tool.

It's a search engine of their database, which continually scans the internet for devices connected and accessible to the internet.

In doing so, you can find and search for so many devices that are just left out in the open. From traffic cams, to webcams, to printers and so much more.

You can search your own organization or affiliations to see if any of your devices are exposed and thus use it for defense. You can also use it for surveillance/recon as an attacker on the red team and the like. 

It's a very versatile tool and has an easily navigatable search engine to find device related to any keywords or filters. 

### VirusTotal

[VirusTotal](https://www.virustotal.com/gui/home/search) is more of a "quick-check" tool used to scan something to see if it's been tagged as malicious or not.

It uses 70 different antivirus engines to check files, URLs, domains, or an existing file hash it's already saved, and it tells us whether any of its engines have flagged it as malicious. 

If what we inputted has already been scanned, it will simply pull up its existing report and show it to us. If what we input is new, it will then actively check and scan our file or URl, etc and save it into its database. 

In that context, its also why it's important that we never input anything that has private or sensitive data within. 

It's also not a perfect tool as it doesn't guarantee safety. However, it's a good tool to get a sort of consensus view on whether something may be malicious or not. 

### Common Vulnerabilities and Exposures(CVE)

[CVE](https://www.cve.org/) and the ["National Vulnerability Database(NVD)](https://nvd.nist.gov/) is essentially a library of known vulnerabilities in tech. 

Each vulnerability has its own specific identifier that uses the format of `CVE-YEAR-NUMBER` like `CVE-2025-55182`. If the vulnerability is significant enough, it may get an alias called a **"Moniker"**

When looking up a CVE, its page gives us information on the vulnerability as well as references to get more info on it. They also are given a score known as "Common Vulnerability Scoring System"(CVSS) whch gives a value measuring its "significance" based off factors like its potential impact, complexity(how easy it is to exploit), as well as availability(how accessible it is to exploit).

Defenders can use this to identify vulnerabilities on a system as well as have priority levels on which ones to patch first. 

Attackers use it in all sorts of creative ways but as soon as a new CVE is published, attackers should immediately be looking for ways to exploit it before the defenders can patch it. 

### Linux Man Pages 


# Module 2 - Linux Fundamentals





# Module 3 - Windows & AD Fundamentals 
