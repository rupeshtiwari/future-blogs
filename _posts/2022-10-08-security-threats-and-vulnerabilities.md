---
title: Security Threats and Vulnerabilities
date: 2022-10-08 00:00 +0000
description: 'IMPORTANT: REMOVE LAYOUT: POST'
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: true
image: https://i.imgur.com/qxXxmBa.png
header:
  image: https://i.imgur.com/zipiW93.png
  teaser: https://i.imgur.com/qxXxmBa.png
  og_image: https://i.imgur.com/qxXxmBa.png
tags:
  - security
  - tutorial
  - beginners
  - azure
---

> Learn about malware, attacks to the network, social engineering attacks

## Malware

Malware can be very problematic that can lock access of files and demand money to pay. It happened to many police office. They had to pay Money to the malware software created to get back the access of the data.

Reference: https://www.youtube.com/playlist?list=PL0bbor_qrUHjy81QzEs0n63duuhQUdr8W

3 Main areas of Malware are:

- **Nuisance**
  Adds, Spyware and Marketing
- **Remote Access / Keyloggers** : Get in to our system and steal password
- **Remote Attacks / DDos**: Use our machine as a botnet and do remote attack against some 3rd party application

### Adware

Malware that is installed on an infected machine to `deliver ads`. Use Malwarebytes Anti-Malware software to prevent Adware.

### Virus

Malicious code that `require user interaction` to install and replicate.

### Spyware

Malicious software that capture `user activity` and reports back. ( keystrokes, web browsing activity etc.)

### Trojan

Seemingly friendly software that contains `hidden` malicious software. Normally, it comes from Remote Access Tools (RAT).

### Rootkits

Malicious code that install itself at the `OS or Kernel` level to avoid detection. They load before OS load while bootup. So anti-virus can not detect it. `Kasper Sky Lab` `TDSSKiller` it can scan boot sector, services and drivers. It is free.

![](https://i.imgur.com/ClM2vva.png){: .full}

### Backdoor

Software that installs for the purpose of opening ports and installing `additional sofwtare`. Backdoor can steal passwords. Full access to the system.

### Logic Bomb

Malicious code that `triggers` after a period of time based on some `date` or `specific activity`. Normally in backup files or codes they hide. An employee who wants to destroy company by installing logic bomb that triggers after he gets fired.

![](https://i.imgur.com/ZAYA7Ki.png){: .full}

### Botnet

Malicious code that infects `large numbers` of hosts for the purpose of launching `large scale attacks` on `specific targets`.

A botnet refers to a group of computers which have been infected by malware and have come under the control of a malicious actor.

![](https://i.imgur.com/PWszcsh.png){: .full}

Command and Control (C&C) servers can control thousands of bots( zombies ) for massive DDoS attacks.

They can target Military, Google, Amazon, Yahoo etc.

### Ransomware

Malicious applications that `scare` or `scam` users into taking some type of `action`. Typically paying the creator for removal.

![](https://i.imgur.com/VJHY1wO.png){: .full}

### Polymorphic Malware

Malware that `changes` on each install to `avoid detection` like changing ports, destination IP addresses etc.

### Armored Virus

Malicious code that is designed to `avoid`, `detection` and `analysis` ( Encryption, obfuscation, additional useless code, etc. )

## Types of Attacks to the Network

4 Categories of attacks:

- Denial of Service: DDoS
- Traffic Capture: Sniffers
- Password Crack: Brute force
- DNS & Host File: Website Spoofing

Here is the list of all attacks:

- Man-in-The-Middle
- Replay
- DDoS
- DoS
- **Smurf Attack**: Broad-cast ping request from victim machine to large number of pcs.
- **Spoofing**: Masquerading as another using their IP address used in DDoS
- **Spam**: using DDoS attacks spam email server
- **Phishing**: Email contains malicious links looks like original ebay or amazon.
- **Spim**: SPAM over instant messaging

  ![](https://i.imgur.com/tr5mwNr.png){: .full}

- **Vishing**: Voice Phishing

  ![](https://i.imgur.com/IFLHQc1.png){: .full}

- **Spear Phishing**: Targeted & Focused phishing campaign
- **Xmas Attack**: Scan of a host to determine what type of system it is. NMap initiates Xmas Attack and creates xmas flags.

  ![](https://i.imgur.com/v3PFAcX.png){: .full}

  NMap software if u give ip address of router then it will give all details of your machine.

  ![](https://i.imgur.com/qfZIHm4.png){: .full}

- **Pharming**: Redirecting a website's traffic somewhere else.  
  If attacker modify DNS Server to redirect the site to Hacker server. Also called as **DNS Poising and ARP Poising**

  ![](https://i.imgur.com/9GZrPM7.png){: .full}

  If attacker modify Client PC to redirect the site to Hacker server.

  ![](https://i.imgur.com/e0XYWMr.png){: .full}

- **DNS Poisoning and ARP Poisoning**
- **Privilege Escalation**: Obtaining elevated privileges
- **Malicious Insider Threat**: Hard to guard this one. Threats from internal employees. They can do logic bomb etc.
- **Transitive Access**: Hard to guard this one. Granted by virtue of being granted access to intermediatory component. If A trusts B and B trusts C then A trusts C by nature of transitivity.

  ![](https://i.imgur.com/5btQMN3.png){: .full}

- **Client-Side attacks**: Attack initiated by client machine. Firewall can not guard against this attack. Layered defences can only save us from client-side attacks. Something like WAF web application firewall on the PC and stop this attack.

  ![](https://i.imgur.com/Fj4nJE4.png){: .full}

- **Password attacks**: Attempting to crack password.

  - Brute Force: keep trying the password till you crack.
  - Dictionary Attacks: use tools like `Crack` to get possible password.
  - Hybrid: brute force attack combined with dictionary attack.
  - Birthday Attacks: Try all combination of alphanumeric value to get the hash value that match with user's password hash value.

    ![](https://i.imgur.com/Pf3iB2g.png){: .full}

  - Rainbow Tables: Precomputed cryptographic hash that gives you large list of hashes to try.
  - Typo Squatting/URL Hijacking: Hackers register domain names with wrong spelling and fool user. Example: Google, Googel, Googgle etc. They just get tons of traffic and they can route them to other site and earn money from them.
  - Watering Hole Attack: Attackers plant malware on the Less secure website where user of targeted company frequently go.

### Man In Middle

Packet sniffing software to intrude the connection.

![](https://i.imgur.com/ihAimsY.png) {: .full}

### Replay

Sniffing the wired network. capture packet and put them back in the connection in the network.

![](https://i.imgur.com/wYC6XXI.png){: .full}

### DDoS

Large scale attack against a target. Botnet is Army of a Zombie

![](https://i.imgur.com/a3ezFvL.png){: .full}

### DoS

Similar type of attack but on much smaller scale.

DDoS attack from China to USA

![](https://i.imgur.com/Pb3qrWQ.png){: .full}

## Social Engineering Attacks

- Shoulder surfing: A person sitting side to you and get your pin
- Dumpster diving: Stealing personal info from dustbin
- Tailgating:
- Impersonating:
- Hoaxes: An email looks genuine on click install virus.
- Whaling: A fake company that can steal your money
- Vishing: A phone call take your personal/company information.

### Reasons for Social Engineering Attacks

- Intimidation
- Consensus or Social proof
- Familiarity/Liking
- Trust
- Scarcity or Urgency

## Wifi Scams

- Rogue access points: Hacker put their WAP and do malicious activity.

![](https://i.imgur.com/8h8uCeC.png){: .full}

- War Driving

![](https://i.imgur.com/BikLpVp.png){: .full}

- Bluejacking: Sending vCard to someone's phone.
- Bluesnarfing: Get data from someone's phone
- IV attacks: Initialization Vector Attacks. Hackers can easily cracked encryptions WEP 24 bit encryption data.
- Packet Sniffing: Someone can use tools (like **WIRESHARK**) to read data from the network's packets. You can look source, destination, protocol, and the actual query, data etc.

  ![](https://i.imgur.com/4YBw1Va.png){: .full}

- NFC (Near Field Communication): Allow to communicate between 2 phone with 2-3 inch near.

![](https://i.imgur.com/I5u5eqD.png){: .full}

- WPS (Wifi Protected Setup) attack: Router pin is compromised.

- WEP/WPA attacks

![](https://i.imgur.com/0E3Y1WB.png){: .full}

## Application Attacks

- Cross-site scripting (XSS): technique to hijack sessions. Browser will run the malicious code because it was served from the server it trust.

![](https://i.imgur.com/SikAW63.png){: .full}

![](https://i.imgur.com/9b1WDBm.png){: .full}

- Cross-site Request Forgery (XSRF)

Here server will run the malicious code because it trust the client.

![](https://i.imgur.com/ynY2Xgu.png){: .full}

- XSS vs XSRF

  ![](https://i.imgur.com/Lg8RhYP.png){: .full}

- SQL injection

Add malicious sql code into the data stream that is running on SQL server. Throw error to crash app, or get info about tables in SQL.

- LDAP injection

LDAP is used to authenticate users. Pass a malicious LDAP query to the webserver that will execute in LDAP server and return additional data.

![](https://i.imgur.com/AZXUygy.png){: .full}

Therefore, sanitize the input value coming from client in webserver before executing to protect this attack.

- XML injection

Inject xml query to alter the path or query of resource. Make a $harmless query in the .ini file present in the server.

![](https://i.imgur.com/24d94JB.png){: .full}

**Fuzzing** used by application to detect security holes.

- Directory traversal/command injection

Inject `./` or `../` to navigate to other directories.

![](https://i.imgur.com/ieJCc4m.png){: .full}

- Buffer overflow

- Integer overflow

- Zero-day

  This are the virus that are not yet fixed by antivirus softwares. Zero-day attack can't be stopped by anti-virus.
  `Stuxnet` attack was using 4 zero-day attack. Google, Microsoft, big private companies, government companies, hackers company they all buy and horde zero-day exploits.

- Cookies and attachments
  EverCookies don't delete ever and they track user's browsing habits.

- LSO (locally shared objects)

Flash Cookies don't delete ever and they track user's browsing habits.

- Flash Cookies

- Malicious add-ons

- Session hijacking

- Header manipulation

- Arbitrary code execution/remote code execution
