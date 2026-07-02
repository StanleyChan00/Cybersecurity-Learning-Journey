# Module 1 - Start Your Cybersecurity Journey

## Search Skills

### Shodan

[Shodan](https://www.shodan.io/) is really good scanning tool.

It's a search engine of Shodan's database, which continually scans and logs the internet for devices connected and accessible to the internet.

In doing so, you can find and search for so many devices that are just left out in the open. From traffic cams, to webcams, to printers and so much more.

You can search your own organization or affiliations to see if any of your devices are exposed and thus use it for defense. You can also use it for surveillance/recon as an attacker on the red team and the like. 

It's a very versatile tool and has an easily navigatable search engine to find device related to any keywords or filters. 

### VirusTotal

[VirusTotal](https://www.virustotal.com/gui/home/search) is more of a "quick-check" tool used to scan something to see if it's been tagged as malicious or not.

It uses 70 different antivirus engines to check files, URLs, domains, or an existing file hash it's already saved, and it tells us whether any of its engines have flagged it as malicious. 

If what we inputted has already been scanned, it will simply pull up its existing report and show it to us. If what we input is new, it will then actively check and scan our file or URl, etc and save it into its database. 

In that context, its also why it's important that we never input anything that has private or sensitive data within. 

It's also not a perfect tool as it doesn't guarantee safety. However, it's a good tool to get a sort of "consensus" view on whether something may be malicious or not. 

### Common Vulnerabilities and Exposures(CVE)

[CVE](https://www.cve.org/) and the ["National Vulnerability Database(NVD)](https://nvd.nist.gov/) is essentially a library of known vulnerabilities in tech. 

Each vulnerability has its own specific identifier that uses the format of `CVE-YEAR-NUMBER` like `CVE-2025-55182`. If the vulnerability is significant enough, it may get an alias called a **"Moniker"**

When looking up a CVE, its page gives us information on the vulnerability as well as references to get more info on it. They also are given a score known as "Common Vulnerability Scoring System"(CVSS) whch gives a value measuring its "significance" based off factors like its potential impact, complexity(how easy it is to exploit), as well as availability(how accessible it is to exploit).

Defenders can use this to identify vulnerabilities on a system as well as have priority levels on which ones to patch first. 

Attackers use it in all sorts of creative ways but as soon as a new CVE is published, attackers should immediately be looking for ways to exploit it before the defenders can patch it. 

### Linux Man Pages 

`Man` stands for "Manual" here. This is a built in manual/reference tool for Linux systems.

It's very simple to use in the CLI. The syntax is simply `man <command>`.

We can use it to learn more and get more information about any command we wish, right there in the terminal. Part of a sample output, provided by TryHackMe, looks like this:

<img width="1231" height="292" alt="Linux Man" src="https://github.com/user-attachments/assets/70aec02d-7402-43a6-8814-0ca846096ccb" />

(Note, the Offensive and Defensive Security Lessons of this module were already completed in Module 1 of the Pre Security Course)

# Module 2 - Linux Fundamentals

## Linux Fundamentals Part 1

As briefly covered in the Pre Security course already, Linux is a core OS that was built open-source. Because it is free to use for everyone, many variants(called distributions) have been built off of it to better specialize for the specific intended task that is needed.

It was based off Unix and is used everywhere from smartphones, to TVs, cloud servers, many IoT devices, and more. This particular lesson from TryHackMe has us using the Ubuntu distro. 

### Some Commands

Many of these commands were covered in depth in the previous Pre Security course [here](../Pre-Security/Module-5-Operating-Systems.md#Linux-CLI-Basics). 

However, in addition to the previous commands taught, this lesson also went over the following:

`echo` - Outputs the same text that we input

`find` - Adding to the notes of the previous course, this lesson taught us the use of the "wildcard" `*`, which allows us to search for a file that we don't know the exact name of. For illustrative purposes, `find -name "*.txt"` would return us the location of every single file that ends in `.txt`. So `*` is a sort of "fill in" character that just means "any characters of any length".

`grep` - This allows us to search a for a specific keyword or term within a file and the terminal will then return all the lines in which that keyword appears. It's useful for getting to specific pieces of data quickly, or filtering data, etc. By default, this command searches only the files within the folder you are in; It does not dive any deeper. Adding `-r` (stands for recursive) would extend this search into ALL the subfolders within your directory. (`-r` ignores shortcut folders while `-R` does not). 

### Shell Operators 

This lesson went over a few operators we can use in the terminal. 

`&` - This allows us to run a command in the background so that we are free to use the terminal for other tasks at the exact same time. It saves us a lot of time for tasks that can take a long time to execute or process like copying a large file. 

`&&` - This allows us to chain commands together. The commands will execute sequentially but if one command fails, the rest will not trigger. 

`>` - This allows us to redirect the output of a commamnd into something else. For example, we can output "hello" via the `echo` command and redirect that into a new file "welcome" via `echo hello > welcome.txt` If a welcome.txt file already exists, the `>` operator will overwrite and replace it

`>>` - This does the same thing as the `>` operator, however it will not overwrite any files. Instead, it will simply add the output onto the bottom of the file as a new line. So in the previous example, if welcome.txt already exists with the word "hey" already in it and we run `echo hello >> welcome.txt` , then the welcome.txt file would now be:

```
hey

hello
```

## Linux Fundamentals Part 2

### Secure Shell(SSH)

We also briefly went over this in the previous course and used it in a lab [here](../Pre-Security/Module-5-Operating-Systems.md#lab---practice-an-authentication-attack-vector-using-the-linux-cli).

But to recap, SSH is a network protocol used to connect devices with a cryptographic encryption. Therefore, the connection is secure and is often used to login remotely to a server or device(like in the lab linked above). 

This lesson had us go over this as well as use their ubuntu Linux VM to login to a remote device using the `ssh` command(syntax format is in the previous lesson) like so `ssh tryhackme@10.67.184.192`

We then logged in using the given password: "tryhackme". Thus the username(from the command) and password(given in the lesson) is both "tryhackme" while the IP is `10.67.184.192`


# Module 3 - Windows & AD Fundamentals 
