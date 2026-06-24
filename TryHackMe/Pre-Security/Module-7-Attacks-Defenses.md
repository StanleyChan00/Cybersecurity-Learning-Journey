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

So in doing this, the word(the plaintext) `Hello` would become `KHOOR`(the ciphertext).

We can also see that the algorithm would in simple terms just be $Ciphertext = Plaintext + X$. And the key would be $X = 3$.

This kind of encryption is very fast and efficient. However, the problem lies in how the keys are sent over and shared to another without anyone else being able to see or use that key as well. 

Encrypting the key itself doesn't work beacuse then you'd have to encrypt the key that unlocks that key and thus you'd end up in an infinite loop. Asymmetric encryption solves this problem. 

### Asymmetric Encryption 

## Become a Hacker



## Become a Defender


