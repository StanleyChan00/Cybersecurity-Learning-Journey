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

Hard links is the number of times in which this file is pointed to. If it's a directory, then it's the number of folders within that directory plus 2(`.` and `..` which points to itself and its parent directory respectively).

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

## Linux Fundamentals Part 3

### Terminal Text Editors 

As refrenced earlier, text editors are a great and more efficient way to handle/manipulate stored text in files. One of these editors is "nano". All we have to do to call upon it is simply use the syntax `nano <filename>`

Here is what it looks like when we open up a file in nano:

<img width="823" height="564" alt="nano sample" src="https://github.com/user-attachments/assets/012a249a-10dd-48d9-ad02-2db81a8bf478" />

Nano is fairly straightforward and simple to use. It works just as one would expect.

However just to note a few of the shortcut commands on the bottom with irregular language:

* "Write Out" saves the changes to the file
* "Justify" essentially is just like wrapping the text in Microsoft Word
* "Cur Pos" brings us to where our current position is with the cursor
* "Read File" allows us to insert the contents of another file into this one
* "To Spell" launches the spell checker

After clarifying these shortcuts, everything is pretty self-intuitive to use. 

This lesson also refrenced "VIM" as another text editor that's more advanced. 

### Transferring and Downloading Files

#### Wget

The `wget` command allows us to download files off the internet. The syntax is simply `wget <URL>`. 

We can also add flags to alter the command a bit. Here are a few:

`wget -O <newfilename> <URL>`  - This allows us to rename the file from its original source name. We can also specify where we want to save it here by adding the path as well.

`wget -P <savedfilepath> <URL>` - This allows us to specify where we are saving this file while retaining its original source name

`wget -b <URL>` - This pushes the download in the background so our terminal is free to use while it's still downloading.

`wget -i <listofURLsfile>` - This allows us to input a file which contains a list of URLs of files that we wish to download. It will then download them all sequentially.

`wget -m <URL>` - This creates an entire clone of a whole website from the URL we input. We "Crawls" through the entire thing and downloads everything so it can be accessed offline. This needs to be used with care due to the invasive and aggressive nature of it. 

#### Secure Copy(SCP)

The `scp` command is essentially what allows us to transfer files between devices securely over the network through the `ssh` protocol. 

Since it uses the same underlying protocol as `ssh`, we still need the username, IP, and password of the remote machine/host we are accessing for the files. 

The syntax is simply `scp <sourcefile> <destination>`, in which case, it will prompt us for the password of the account we are accessing.

With this command, we can either transfer files from a remote device to ours or transfer files from our local device to a remote computer. Either works; We just have to ensure the syntax order is correct for the source/destination files. 

It will look like this:

`scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt` - This transfers `important.txt` from our device to the "Ubuntu" user of IP `192.168.1.30`. It will also be renamed as `trasnferred.txt`.

Or like this:

`scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt` - This transfers the `documents.txt` from a remote device onto our local device with the new file name as `notes.txt`

#### Hosting a Web Server to Share Files

Because Ubuntu comes with Python3, we can use Python to host a web server to share files to other devices.

The syntax is very simple. All we do is call upon Python to run their HTTPServer, which will immediately start up running the module and allow us to serve files!

`python3 -m http.server` - The `-m` flag tells python to run the `http.server` module.

By default, when we enter this command, this will host the **entire directory** that we are currently in. We need to be mindful of this to not ensure we are not sharing sensitive data.

We can specify a certain path to share via the `-d` flag and input the file/directory path if we would like as well. In which case, it would look like: `python3 -m http.server <port> -d <filepath>`

It also defaults to port 8000, but we can also alter that in the command.

Now, our server is live while the process is running. Now anyone, so long as they know our IP and port number, can access those shared files. It will look something like this:

<img width="817" height="847" alt="Python3 Web Server" src="https://github.com/user-attachments/assets/3eeceb35-bd5c-4b43-809d-6b1bd48a31a9" />

The top is what it looks like hosting the server in the terminal and the bottom is obtaining the file.

To obtain the file, we used the `wget` command and input the IP, as well as the port number, to transfer over the task3 file. 

### Processes 101

This is the equivalent of the "Task Manager" from Windows and allows us to see the processes that our computer is currently running as well as more information about those processes.

We do this via the `ps` command, which stands for "Process Status". A sample output from our VM looks as follows:

<img width="314" height="86" alt="Linux ps" src="https://github.com/user-attachments/assets/ed4dfec1-3576-4536-b378-d1ec024b91f0" />

In it, we can see the "PID" which stands for Process Identifier. It's important to note that this identifies the processes incrementally. So if one process has a PID of 45, the next one will be 46 and so on. 

This lesson didn't go over the rest of the column data types. However to cover them quickly, we have Teletypewriter(TTY), Time, and Command(CMD). Which tells us the terminal being used by the process, the accumulated amount of time used by the CPU for that process, as well as the command name used for that process respectively. 

We can get even more information about these data types, as well as reveal a lot more processes(including system processes or processes run by other users, etc), by the `-ef` and `aux` switches.

In essence, the main difference between these two switches are that `aux` will tell you more about CPU/Memory usage while `-ef` tells you more about the parent processes and relationships, as in what started these processes. 

We can also use the `top` command which is most akin to the task manager in giving us a dashboard of all the processes running in real time. 

We can end processes via the `kill` command by simply typing in the PID of the process we want to end after the command. There are 3 main signals we can add to the command to alter how the process is ended:

* SIGTERM - This is the default that is used with the command. It asks the process to end but allows it to clean up properly before closing shop. The catch though is that sometimes the process will not close due to a variety of reasons like corrupted files.
* SIGKILL - This authoritatively ends the process forcefully. 
* SIGSTOP - This simply pauses the process. `SIGCONT` would continue or start it back up again.

#### The First PID 

The very first process that begins when the system boots up is `systemd` which has a PID of 1. This is the initializer and acts as the parent process for every single other process that we run on our device. It's essentially the "root" of processes. 

This also creates one big global namespace by default. A namespace being how the OS splits up its resources and isolates departments of our system such that processes can only see and interact with other processes within its own namespace. 

#### Background Processes and Daemons 

We can run many processes in the background while our terminal remains free to use. We can start these background processes on our own or have it automatically run when the system boots up as daemons, which are just continually running background processes that run outside of the terminal. 

We can manage these background processes via the `systemctl`, standing for "System Control", with the syntax of `systemctl <option> <service>`.

The service is simply the process we want to manage, like apache for example(a web server), while the option is one of 5 common arguments we can input.

* Start
* Stop
* Enable
* Disable
* Status

With this command, we can now manage these background processes. 

We can also manually push something from the terminal foreground into the background via the [`&`](#shell-operators) operator. Which, as we covered, pushes a command into the background. 

In doing so, it will output the ID of the process while it runs in the background. This way, copying a large file for example, can run in the background while we still have access to the terminal.

If a script is currently running in our terminal, we can pause it with `CTRL + Z` and then use the `bg` command to throw it into the background while the inverse `fg` brings it back into the foreground. 

The syntax for both of these would be either `bg` or `fg` followed by a `%<jobnumber>`. If we have only one job running or paused, just typing it on its own will also work. 

#### Cron and Crontab

`crond` is daemon that is constantly running and checks every minute if there is a scheduled job it needs to do.

We can use this to schedule and automate processes that we don't want to have to do manually. This could be launching specific apps like spotify or running a backup that automatically occurs at specific times. 

`crontab` is the file used by `crond` to check what jobs it has scheduled. So if we want to edit or add any jobs, we can go to the `crondtab` file via `crontab -e` to do so. This opens a text editor of the file for us. 

The format taken for these commands can be a bit hard to read and make. So we can use a [crontab generator](https://crontab-generator.org/) to make the commands for us.

We just pick the command and time in which we want it to be automated to. Then we add it to the crontab file. 

An example of this will look like:

`0 12 */10 * * cp -R /home/cmnatic/Documents /var/backups/ >/dev/null 2>&1`

Which copies our documents folder and places it inside our backups folder every 10 days at noon, essentially backing up our documents every 10 days. 

For reference, the first section of the command is the timing. The second is the actual command and the last is where we want any outputs to go(Like error messages, etc). In this case, all the output is getting muted.

### Repositories 

Repositories are just folders. However, in this case of Linux, they act as storage for software or packages that we can use or download. 

The vendor of our OS is responsible for maintaining our repos and ensuring everything there is safe, stable, and updated. We however can add Community repos to our system if we want more functionalities.

This is one of the benefits of the open-source nature of Linux.

To manage our repos, we use the `apt` command and any extra modifications thereof. We can search using the `search` command for software packages in our repos by typing in keywords to search for. We can use `show` to get more details on a specific package. 

We can use `update` to check if there's packages we have that's not updated to the latest version yet and then use the `upgrade` command to actually update it.

#### Adding Repos and Downloading Software

We can also use the `add-apt-repository` command to add community repos not already on our system. 

A nice benefit of downloading software through adding it into our repos is that the `apt` command will automatically be checking it for updates for us. 

So, for example, if we wanted to download the "Sublime" Text Editor as a repo, there's a few things we have to do.

For one, developers use "GPG" keys to achieve integrity(of the [CIA triad](../Pre-Security/Module-7-Attacks-Defenses.md#the-cia-triad)) and ensure nothing was altered from what they intended to be downloaded. 

We need to download these keys from the developer so that that we can trust it has not been altered. The command would look like so:

`wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -`

From here, we want to make a new file for the repo of the 3rd party we want to download from in the /etc/apt/sources.list.d file path. 

And in that file, we can finally add Sublime Text repo URL. 

Now, the last two steps would be using the `apt update` command to recognize this as a repo and finally then the `apt install` command to install the text editor.

### Logs

Lastly, various types of logs for software, applications, or the system are found in the /var/log directory.

Operating Systems usually have a great process of managing these logs and preventing htem from overflowing storage by an automatic rotating system which deletes, archives, or compresses olds logs, making space for new ones. 

Here we can see some log files for a few services.

* Apache2 Web Server
* Fail2Ban (Monitors stuff like attempted brute force attacks)
* UFW (Like a firewall)

<img width="626" height="457" alt="Logs" src="https://github.com/user-attachments/assets/49e08f8c-21fa-4319-9890-1352eb26425e" />

There we can get important security data or status updates from those applications. For example, we can see all the requests made to our Apache Web serevr. We can see error logs, access logs and more. 

It's a great place to monitor the health and security of our systems.

# Module 3 - Windows & AD Fundamentals 
