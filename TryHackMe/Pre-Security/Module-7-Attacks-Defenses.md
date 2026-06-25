# TryHackMe Pre Security - Module 7: Attacks and Defenses

## The CIA Triad

As we already briefly went over in Module 5, CIA stands for **Confidentiality**, **Integrity**, and **Availability**. 

Essentially all of Cybersecurity revolves around ensuring that these three elements are secure either through attacking these points or defending them. 

### Confidentiality

This is the pillar that ensures that sensitive data is ONLY viewable to those with authorized access to it. 

**Any** potenial leak that allows **anyone** else to be able to access these contents without permission is a vulnerability to our security and said vulnerabilities can have disastrous effects through a malicious actor.

From login credentials, to bank information, to identity thefts, to personal data and more. It's crucial to ensure confidentiality is achieved.

### Integrity

This pillar ensures that no data can be modified without proper authorization.

If integrity is compromised, we can never trust anything that we are interacting with. Any of it could have been altered by a malicious actor. 

In doing so, we may be sending bank transfers or sensitive data to unintended people without even knowing it. We may be receiving false or altered data and more. 

So it's crucial to ensure that integrity is achieved so that we can have confidence in what we interact with.

### Availability

Availability is the pillar in which services or data is available for use when it has to be needed. 

For example, a company's service may need to be online and available for use constantly. Whether that reasoning be for security/health or for financial motivations as downtime would cut off revenue for the entire time that it is down(along with the effects in PR & customer satisfaction). 

Thus, shutting down this service and making it unavailable for use is an attack vector that needs to be protected against. 

Not doing so could cause massive financial implications or damages to livelihoods.

## Cryptography Concepts

Cryptography is a huge way in which we achieve confidentiality. In essence, it's the process of encrypting data such that no one can read the actual content other than the intended parties. 

This is done through encryption methods, which is just scrambling data in a way that hides it to those whom don't have the "key" to descramble it and decipher the contents. 

There are two types of Encryptions: **Symmetric** and **Asymmetric** Encryption. But first, some simple terms covered in this lesson:

* **Plaintext:** This is the unencrypted text that is readable.
* **CipherText:** This is the encrypted text that is not readable and hides the actual data.
* **Key:** This is what allows us to decipher the encrypted text and turn it into readable data or to encrypt data and turn it into unreadable data
* **Algorithm:** This is how the key is used to decipher the encryption(or to encrypt data itself). It's the formula for encryption/decryption. 

### Symmetric Encryption 

The distinguishing factor of this type of encryption is that the **same** key used for encryption will be used for decryption. Meaning that the sender and receiver **both** use the same exact key to encrypt and decrypt the data. 

This is like locking a safebox and handing it over to a friend who also has a copy of the key used to unlock that safe. An example of this type of encyrption is the age old Caesar Cipher which is visually illustrated in the picture below:

<img width="80%" height="80%" alt="Caesar Cipher" src="https://github.com/user-attachments/assets/90a707ee-ef6a-4dae-b82f-ff67fc222f9b" />

It's a very simple encryption. In the image, for example, every letter in the data we want to encrypt will just get shifted 3 letters forward. 

* `A` becomes `D`
* `B` becomes `E`
* etc

So in doing this, the word `Hello`(the plaintext) would become `KHOOR`(the ciphertext).

We can also see that the algorithm would in simple terms just be $Ciphertext = Plaintext + X$. And the key would be $X = 3$.

This kind of encryption is very fast and efficient. However, the problem lies in how the keys are sent over and shared to another without anyone else being able to see or use that key as well. 

Encrypting the key itself doesn't work beacuse then you'd have to encrypt the key that unlocks that key and thus you'd end up in an infinite loop. Asymmetric encryption solves this problem. 

### Asymmetric Encryption 

The difference here is that the encryption and decryption keys are not the same. The encryption key is public and shared to anyone while the decryption key is kept secret.

In this case, anyone can encrypt a message using this encryption but ONLY the holder of the private key can decrypt and read that message. 

This solves the problem of Symmetric encryptions because there is no longer a need to share the secret key. There is a public and a private key and *only* the public key is needed to encrypt and send secure data to another.

Anything I need to send a secret message to my friend is through my friend's public key. I use that key to "lock" my message and no one else can open that lock besides my friend or whoever that has that private key. 

The downside though is that it's extremely slow and requires more CPU power. So large files or services like streaming can't use it. However, **Hybrid encryptions** are used which allows for a lot more flexibility.

Hybrid Encryptions combined both these methods by, in essence, using asymmetric encryption to create a secure channel in which the symmetrically encrypted key as well as the symmetrically encrypted data files can be shared securely.

This combines the speed and efficiency of symmetric encryptions with the security of asymmetric encryptions. HTTPS for example uses hybrid encryption. 

## Become a Hacker

As covered in Module 1, offensive security has the role of actively attempting to break into systems, in a controlled manner, to find exploitative weaknesses that can be patched up.

In order to perform in this role effectively, we need to place ourself in the mindset of a malicious attacker and constantly be asking questions like 

* "What is exposed? What can be exposed?"
* "What can be accessed? What can we do with that access"?
* "What assumptions does the system make in how we will act? Can we act differently in a way the system does not expect?"
* And so on.

Some quick key terms:

* **Red Teaming:** A real world test of a security’s defense that acts like an authentic malicious attacker. As in, it happens by suprise/without notice and tests the system/defense team as a whole. 
* **Penetration Test**: This is like a structured inspection where every vulnerability is identified and exploited
* **Vulnerability:** A weakness in a system that can be exploited
* **Exploit:** Taking advantage of a vulnerability in a system
* **Scope:** The boundries of what is allowed during offensive security "attack"

### Lab

This lab had us "attack" a new business owner's website.

Here, we started off by attempting to identify any hidden pages that may not have been properly blocked off from the public. In this case, we can just keep trying different URLs like `http://www.onlineshop.thm/admin`, etc. 

This can be time consuming and impractical in real world scenarios. 

But there is a tool ethical hacker's use called `Gobuster` which is used in the terminal and allows us to scan a URL for a set of defined keywords as hidden pages.

The command for it may look like this:

`gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt`

`gobuster` calls the gobuster tool.

`dir` tells the command to specifically look for directories/files. It directs the command in scanning for the hidden pages we are looking for. 

`--url http://www.onlineshop.thm/` specifies the target we want to scan

`-w` stands for wordlist and tells the command that the following is where it will find all the words to scan that target URL for. 

`/usr/share/wordlists/dirbuster/directory-list.txt` This is the file path to the wordlist we are using to scan. 

We then used that command in the terminal. The login web page popped up with a 200 status code, meaning it connected to the page successfully. 




## Become a Defender


