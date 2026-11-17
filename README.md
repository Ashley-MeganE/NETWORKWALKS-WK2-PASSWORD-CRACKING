<h1 align="center"> Password Cracking with John the Ripper and Networkwalks Tools </h1>

|  |  |
|:---| :---|
|**Name**| Ashley-Megan Ikhialose Ehiede |
|**Batch Number**| 084|
|**Modules Completed**| PM1: Password Cracking with JTR <br> PM2: Password Cracking with NW Tools  |
|**Target**|Files Provided by Networkwalks|
|**Permission obtained from target?**| Yes |
|**Phases Covered**|Phase 3: Gaining Access |
|**Tools Used** | John The Ripper <br> Networkwalks Tools <br> OnlineHashCrack PDF Hash Extractor|

## Liability Disclaimer
*I have performed these activities only on the systems, files & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorized access is a crime even when nothing is damaged.*

## Introduction 
John The Ripper is a tool used by cybersecurity engineers to test password strength and recover lost credentials. In this lab I used this tool to crack the password of a file provided to me by Networkwalks. Afterwards, I used Networkwalks' tools to crack the password of a second file. 

### Activities Executed
I downloaded the first file, named `My Locked PDF1`. An initial attempt to open the file confirmed that it was encrypted with a password. Opening OnlineHashCrack's PDF Hash Extractor, I extracted the hash, copied it and put it in a new `.txt` file. Opening and starting a new attack on this file in John The Ripper application gave me the correct password within seconds: `good-luck`. I entered this into the file's password prompt, and it granted me access.

For the second module, I downloaded the second document, `My-Locked-PDF1` and uploaded it into the PDF tab of Networkwalks' Hash Calculator tool to extract its crackable password hash. It returned the hash value within seconds which I copied. I opened NW's Password Cracker, pasted the previously copied hash and began a dictionary attack. In less than a minute it returned the password for the file, `password1`. Typing this in unlocked the file. 

## Lessons Learned 
* **Weak Passwords Fail Almost Instantly:** Simple, predictable passwords (like `password1` or common dictionary phrases like `good-luck`) offer virtually zero protection against automated dictionary attacks and can be cracked in seconds.
* **Offline vs. Online Cracking Speed:** Once an attacker extracts a password hash from a locked file, they can run millions of guesses offline using tools like John the Ripper without triggering account lockouts or alerting the file owner.
* **Hash Extraction Comes First:** Password-cracking tools cannot read encrypted files directly. Security analysts must first extract the underlying cryptographic hash (using utilities like `pdf2john` or an online hash extractor) before running an attack.
* **Defense Requires Length and Complexity:** Strong passwords need sufficient length, randomness, and mixed character types (uppercase, lowercase, numbers, and symbols) to resist both dictionary wordlists and brute-force attacks.

