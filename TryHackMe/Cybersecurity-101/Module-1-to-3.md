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

### Flags and Switches 

In many of the commands covered [here](../Pre-Security/Module-5-Operating-Systems.md#Linux-CLI-Basics), we were able to add "modifiers" which slightly altered how the commands would execute. 

For example, with `ls` we could add `-a` to show all the hidden files in a directory rather than the default command of `ls` not displaying them.

These "modifiers" which allow for us to add extra arguments to the commands are called **flags** or **switches**.

These flags start with a `-` followed by their specific identifiers.

To get a list of possible flags a command can accept, we can type in `--help` after a command that accepts flags.

That of which, a sample output will look like the following:

<img width="1034" height="872" alt="--help" src="https://github.com/user-attachments/assets/6dbe1a1d-976e-43cc-a23d-f93b567989ad" />

We can also use the [Man pages](#linux-man-pages) to get more information.

### Managing Files

Some more commands, specifically in relation to managing our file systems:

`touch` - This creates a file It's a very simple command and just requires an inout for the file name like `touch <filename>`. Also note that the file created will be blank and commands would be needed to add to it or a text editor(like nano) can be used. 

`mkdir` - This stands for "make directory" and creates a folder for us. We just title that folder within the input as so `mkdir <directoryname>`

`cp` - This stands for "copy" and allows us to copy a file into a destination. That destination can be an entirely new file or overwrite an existing one. It takes two inputs - the copied file and the destination and is written as `cp <copiedfile> <destination/newfilename>`. Adding the `-i`(standing for interactive) allows for a warning before overwriting a file

`mv` - This stands for "move" which not only allows us to move files but also rename them. Like `cp`, it takes two inputs - the initial file and the destination/new file name and looks like so: `mv <initialfile> <destination/renamedfile>`. Same as with `cp`, if the new filename already exists, it will be overwrittem so adding `-i` beforehand allows you to confirm before doing so.

`rm` - This stands for "remove" and allows you to permanently delete a file or folder. We simply just input what we want to delete. If we want to delete a folder, we have to use the recursive flag `-r` which deletes the folder and everything inside it. `-d`(stands for directory) if the folder is specifically empty and we want to confirm we are deleting an empty folder. 

`file` - This command tells us what type of content is in a file. Because Linux, unlike other OSs, don't really need file extentions, `file` is used to tell us what type of file we're dealing with: text, media, etc.

Note that all these commands can take entire file paths as inputs for the arguments.

### Permissions 101

As we understand already, files can have specfic permission levels. Meaning certain users or groups of users can have more access to files or folders. 

We can see these privilege levels using the `ls -l` command. A sample output provided by the lesson looks like the following:

```
tryhackme@linux2:~$ ls -lh
-rw-r--r-- 1 cmnatic cmnatic 0 Feb 19 10:37 file1
-rw-r--r-- 8 cmnatic cmnatic 0 Feb 19 10:37 file2

```

Just as a quick overview, there's 7 total columns of data types listed when the `ls -l` command is used. 

|Permissions|Hard Links|Owner  |Group  |File Size|Last Changed|File Name|
|:---------:|:--------:|:-----:|:-----:|:-------:|:----------:|:-------:|
|-rw-r--r-- |1         |cmnatic|cmnatic|0        |Feb 19 10:37|file1    |

Hard links is the number of times in which this file is pointed to. If it's a directory, then it's the number of folders within that directory plus 2(`.` and `..` which points to itself and its parent directory respectively.

Owner is the user who currently owns that file. Group is the group of users relevant to the permissions of this file(explained more in a second). File size is the size of the file and in this case is just 0(the human readable flag was also used in this command so it's not bytes being represented, as a note).

Last changed is when the file was last modified and the file name is the last column. 

#### Permissions via the "list long" Command 

As we can see, the permissions came out as `-rw-r--r--`. There are 3 sections of data here within this output.(Technically 4 if we include the first character. Here is a `-` meaning the item we are looking at is a file. `d` is a directory. `l` is "link" as in it is a shortcut file)

Ignoring the first character, it is `rw-r--r--`. Each 3 characters represent the permission levels of the owner, group, and all other users respectively.

It comes in the format of `rwx` meaning:

* Read: Permission to read the file
* Write: Permission to alter the file
* Execute: The file is treated as a script and this gives permission to execute the program inside it

If instead the content is a directory:

* Read: Permission to use `ls` and see what is inside the directory
* Write: Permission to change or modifer what is or is not inside the directory itself.(ex mv, cp, rm, etc).
* Execute: Permission to enter anything inside the directory like via `cd`

So, with the `ls -l` command, we can thus see the permission levels of the files/directories. The first 3 characters represent the permission levels of the owner of that file. The next 3 characters represent the permission levels of the group associated with that file. While the last 3 characters represent the permission levels for all other users.

**Groups:** Groups are, as it sounds, collections of users created by the system administrator. For example, within an organization, the finance department may be the finance "group". 

Each file can ONLY be associated with **one** group at a time chosen by the owner of the file(Note that they can only assign a file to a group that they belong to). That group is named in the `ls -l` command as seen above and the permission levels for the "group" section represent the permission levels for that specific respective group. "Others" represent all other users besides that group and the owner. 

#### Switching Between Users

To switch between users, we can use the `su` command which stands for "switch user". We simply input the username after `su` and then the system will prompt us for the password of the user.

We can also add the `-l` flag, which stands for "login", which essentially starts us up as if its a new login session. As in, we go to the new users home directory and loads all the settings and environments for that user rather than just staying where we were. 

#### Permission Numeric Values

Each of these permissions have a numeric value that adds together for the owner, group, and all other users respectively. In doing so, we end up having a sort of "status code" which allows us to quickly look at a value and see the permission levels of a file/directory at a glance. 

Here are the values:

* Read = 4
* Write = 2
* Execute = 1

If the owner, for example, had the values `rwx`, then that would be $4 + 2 + 1=7$. So the owner's value would be 7. 

Say the group and other uses also had `rwx`, then they both would also have the value of 7. So the numeric permission for this specific file would be `777`, meaning all users can do everything on this file(read, write, execute). 

`622` would mean that the owner can read and write while the group and other users can only write. `700` would mean ONLY the owner has access to everything. 

The values for read, write, and execute are such that it's easy to see what permissions are allowed from a glance because each value has only one unique combination of values that add up to it.

### Common Directories 

#### /etc

This just stands for "etc" as in "etcetera" but its an incredibly important root directory as it is the commonplace location to store the system files used by our OS.

For example, the `sudoers` which defines user privilege and more stored in the file in this directory. `passwd` and `shadow` is also stored here which contains information about our user accounts and passwords(encrypted). 

#### /var

This stands for variable data and as it sounds, holds data that dynamically changes depending on the application or tasks the system is doing. Managing or creating files here manually rarely hppens but the system updates and uses it automatically. 

For example, log files would be here.


#### /root

This is just the home directory for the system administrator.

#### /tmp

This stands for "temporary" and as it sounds, stores temporary data similar to the RAM's role in hardware. Thus, the content here is volatile and cleared out each time the computer is restarted. 

# Module 3 - Windows & AD Fundamentals 
