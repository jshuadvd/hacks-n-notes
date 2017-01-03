# Security

## Bug Bounty programs

- [BugCrowd](https://bugcrowd.com)

## Encryption
> scramble code with a key

- Today's encryption uses 256 bit keys

### Symmetric key 
> When sender and receiver use the same key

- eg. Ceasar's cypher
- The key has to be agreed before time

### Asymmetric key
> used in open communications like the Internet

- Consists of a public key that can be exchanged with anybody and a private key that isn't shared
- The public key is used to encrypt data and anybody can create a secret message
- The secret can only be decrypted by a computer with a private key

## IEEE OC CyberSecurity SIG
> https://cssig.brats.com
> Chair Arthur Schwarz

### Techniques

#### SSH Pivoting
- is to move between subnets piping traffic from one subnet to another

- `ssh -Local`
- `ssh -Remote`
- `ssh -Dynamic`

#### SSH lateral attack
- moving within the same subnet


### Tools

- [MetaSploit](https://www.metasploit.com/)
- [Armitage](http://www.fastandeasyhacking.com) - GUI for MetaSploit
- [Dirty COW](https://dirtycow.ninja/) - "Copy on Write" Linux vulnerability


### commands

- `ifconfig` to get ip address
- `locate ifconfig` to get the directory where the `ifconfig` or any other command is located.
- `netdiscover -r <inet>` discover how many machines connected to the local network
- `nmap <ip address>` shows ports exposed in a machine
- `netstat`
 
## ACM Cyber Security
 
 Brian Wallace - Cylance
  
 The Diversity of the Cyber Threat Landscape
 github.com/bwall
 @botnet_hunter

- APT (Advanced Persistent Threats)

### social engineering
- eg. hacking an email to get the VPN password

### Spray and Pray Spam
- Offered as SaaS too
- emails, twitters

### Credential Phishing
- eg. PayPal

### Spear Phishing
- specific targets
- you can harvest info from user from public social media
 - Operation Cleaver -> can use trojan horse app, posing as a recruiter

### USB Drops
- "lost and found" USB stick with malware
- [USB Rubber Ducky](http://usbrubberducky.com/#!index.md)
- [Teensy-LC](http://www.pjrc.com/teensy/teensyLC.html)

### Remote Exploitation
- software vulnerabilities
- unconfigured devices can be a gold mine for attacker
- IPv6 will make the web more vulnerable

### Default Credentials
- eg. root/root
- this is how the Mirai DNS attack was done through IoT

### Over Exposed Services
- eg. hotel wifi
- ANTLabs InnGate (hotel Wifi)
- [RSYNC](https://en.wikipedia.org/wiki/Rsync) daemon

### Exploits
- Adobe Reader is very vulnerable. Watch out with PDFs you don't know
- patching helps

### Man in the Middle (MITM)
- in a coffee shop wifi, trick you or your computer to proxy through them.. 
- tool [Evilgrade](http://tools.kali.org/sniffingspoofing/isr-evilgrade)

### Public WiFi
- MITM
- Airplane, coffee shop, restaurant wifis
- anything not encrypted is at risk
- use VPN can help when using public WiFi
- or not use the public WiFi

### Femtocells
- [StringRay](https://en.wikipedia.org/wiki/Stingray_phone_tracker) tool from law enforcement to listen to calls
- hack the femtocell and can get MITM access to a phone even without WiFi

### Lateral Movement

#### Credential Theft
- Passwords

#### Cached Credentials
- Isass.exe in Windows stores username/passwords
- [Mimikatz](https://github.com/gentilkiwi/mimikatz) to pull data from Isass.exe

#### Credentials from the Network
- LLMNR, NBT-NS and MDNS can be abused on Windows to leak encrypted creds
- [Responder](https://github.com/SpiderLabs/Responder) tool

#### Credentials in Shared Documents
- creds in a script, file, github, slack
- attackers may be paid by the hour to dig into your stuff until they find something

#### Abusing Shared Resources
- they can modify wikis, word documents, exes, etc.

### Destroy Data

### Encrypt Data
- Ransomeware .. encrypt files in a system and ask a ransome for that
- Bitcoin or other difficult to de-anonymize payment method

### Steal Data
- it's possible to encode data in simple words eg. Taylor Swift lyrics using machine learning

### Protection
- set protection like onion layers
- train your personnel
- [how to setup a VPN](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-16-04)


### DDoS (Distributed Denial of Service)
> When attackers flood a web server with requests

- A **BotNet** is a network of infected computers that can be used to cause DDoS attacks.

 ## meetups
 - OWASP-OC http://www.meetup.com/OWASP-OC/  ACMOC20OFF
 