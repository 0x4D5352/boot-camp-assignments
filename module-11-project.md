    Cybersecurity
Module 11 Challenge Submission File

Network Security Homework
Make a copy of this document to work in, and then fill out the solution for each prompt below. Save and submit this completed file as your Challenge deliverable.


Part 1: Review Questions 

Security Control Types

The concept of defense in depth can be broken down into three security control types. Identify the security control type of each set of defense tactics.

 Walls, bollards, fences, guard dogs, cameras, and lighting are what type of security control?

Physical


Security awareness programs, BYOD policies, and ethical hiring practices are what type of security control?

Administrative


Encryption, biometric fingerprint readers, firewalls, endpoint security, and intrusion detection systems are what type of security control?

Technical


Intrusion Detection and Attack Indicators

What’s the difference between an IDS and an IPS?

IDS - Intrusion Detection System - sits passively on a network (typically by sending a copy of all data traffic from the router/switch to the IDS) and looks for suspicious or malicious activities, but cannot directly interact with the network traffic or make attempts to stop it.

IPS - Intrusion Prevention System - Works in a similar way to an IDS, and could be seen as being a superset of an IDS (i.e. all the features of an IDS exist within an IPS, but an IPS has features an IDS does not). The distinctions being that an IPS is more often placed within the network traffic line, which allows it to take actions to try and stop or slow down intrusions.


What’s the difference between an indicator of attack (IOA) and an indicator of compromise (IOC)?

Indicator Of Attack - A sign that someone is attempting to breach your defenses. Port scanning, phishing attempts, login brute force attempts, etc. Usually used in the present tense, where the attack is currently happening. 

Indicator of Compromise - A sign that your defenses have successfully been breached. Foreign outgoing traffic, malicious downloads, ransomware, etc. A past tense label - the attack has happened in the past, and now you have to deal with the consequences.


The Cyber Kill Chain

Name the seven stages of the cyber kill chain, and provide a brief example of each.

Stage 1: 

Reconnaissance - Initial intel gathering, where the attacker uses public (or private but otherwise available) information to aid in the attack on the victim. E.g. linkedin, dark net leaks


Stage 2:

Weaponization - Determine avenues of attack, profile target’s possible defenses and countermeasures, and develop a strategy to succeed in the attack. E.g security infrastructure, network topology


Stage 3:

Delivery - Getting the payload onto the target system (such as via email, website, etc).


Stage 4:

Exploitation - Begin secondary enumeration phase and continue compromising the victim’s systems. Avoid security controls and establish a stronghold in the network for final exploitation.


Stage 5:

Installation - Gathering all your ducks in a row, as it were. Installing malware, backdoors, and system level controls to create a persistent presence on the system.


Stage 6:

C2 (Command & Control) - Using a command channel like IRC or a HTTPS server to remotely control the victim’s computer


Stage 7:

Actions on Objectives - aka “Hands on Keyboard”. When the attacker can successfully perform whatever their main goal was. Exfil of data, activation of malware, creation of “zombies” for a botnet, etc.


Snort Rule Analysis

Use the provided Snort rules to answer the following questions:

Snort Rule #1

alert tcp $EXTERNAL_NET any -> $HOME_NET 5800:5820 (msg:"ET SCAN Potential VNC Scan 5800-5820"; flags:S,12; threshold: type both, track by_src, count 5, seconds 60; reference:url,doc.emergingthreats.net/2002910; classtype:attempted-recon; sid:2002910; rev:5; metadata:created_at 2010_07_30, updated_at 2010_07_30;)


Break down the Sort rule header and explain what this rule does.

alert = the command verb, saying to raise an alert when the conditions are met

tcp = the protocol to be watching out for

$EXTERNAL_NET = an environment variable, set to encompass all IP addresses not listed as part of the home network

any = the ports to watch, in this case all ports

-> = the directionality arrow, showing that we’re looking for connections FROM the left side TO the right side. IPs before this are source, IPs after are destination

$HOME_NET = another environment variable, set to encompass all IP addresses listed as part of the home network.

5800:5820 = the ports to watch, in this case within the range starting 5800 and ending 5820

Everything after that is the alert message, which i believe doesn’t count as part of the header, but summarizing it: the alert message (“msg”) is saying that an attempt to scan for virtual network computing access has occurred. After that there is additional data that is likely used by analysis tools further down the signal path.


What stage of the cyber kill chain does the alerted activity violate?

I would say this qualifies as Reconnaissance - port scans are an attempt to gather more information on the target. I could also see this as a form of Weaponization, where attack vectors are being determined, but I think it is most likely Recon.


What kind of attack is indicated?

Potential VNC scan - VNC = Virtual Network Computing https://en.wikipedia.org/wiki/Virtual_Network_Computing


Snort Rule #2

alert tcp $EXTERNAL_NET $HTTP_PORTS -> $HOME_NET any (msg:"ET POLICY PE EXE or DLL Windows file download HTTP"; flow:established,to_client; flowbits:isnotset,ET.http.binary; flowbits:isnotset,ET.INFO.WindowsUpdate; file_data; content:"MZ"; within:2; byte_jump:4,58,relative,little; content:"PE|00 00|"; distance:-64; within:4; flowbits:set,ET.http.binary; metadata: former_category POLICY; reference:url,doc.emergingthreats.net/bin/view/Main/2018959; classtype:policy-violation; sid:2018959; rev:4; metadata:created_at 2014_08_19, updated_at 2017_02_01;)


Break down the Sort rule header and explain what this rule does.

alert = command verb - set an alert

tcp = protocol to watch

$EXTERNAL_NET = environment variable for external network IPs to watch as source

$HTTP_PORTS = environment variable for reserved HTTP ports (80 for HTTP and 443 for HTTPS)

-> = traffic direction indicator

$HOME_NET = environment variable for internal network IPs

any = ports to watch on destination IP, in this case any


What layer of the defense in depth model does the alerted activity violate?

Technical


What kind of attack is indicated?

A potentially malicious executable file was downloaded via HTTP


Snort Rule #3

Your turn! Write a Snort rule that alerts when traffic is detected inbound on port 4444 to the local network on any port. Be sure to include the msg in the rule option.

alert tcp $EXTERNAL_NET 4444 -> $HOME_NET any (msg:”Metasploit Port Or Trojan”;)



Part 2: “Drop Zone” Lab

Set up.

Log in using the following credentials:

Username: sysadmin
Password: cybersecurity

Uninstall UFW.

Before getting started, you should verify that you do not have any instances of UFW running. This will avoid conflicts with your firewalld service. This also ensures that firewalld will be your default firewall.

Run the command that removes any running instance of UFW.

$ sudo ufw disable


(a followup of sudo ufw status should list “Status: inactive”)


Enable and start firewalld.

By default, the firewalld service should be running. If not, then run the commands that enable and start firewalld upon boots and reboots.

$ sudo systemctl enable firewalld
$ sudo /etc/init.d/firewalld start


Note: This will ensure that firewalld remains active after each reboot.


Confirm that the service is running.

Run the command that checks whether the firewalld service is up and running.
  
$ systemctl status firewalld 


List all firewall rules currently configured.

Next, list all currently configured firewall rules. This will give you a good idea of what’s currently configured and save you time in the long run by ensuring that you don’t duplicate work that’s already done.

Run the command that lists all currently configured firewall rules:

$ sudo firewall-cmd --list-all


Take note of what zones and settings are configured. You may need to remove unneeded services and settings.

List all supported service types that can be enabled.

Run the command that lists all currently supported services to find out whether the service you need is available.

$ sudo firewall-cmd --get-services


Notice that the home and drop zones are created by default.

Zone views.

Run the command that lists all currently configured zones.

$ sudo firewall-cmd --get-zones


Notice that the public and drop zones are created by default. Therefore, you will need to create zones for web, sales, and mail.

Create zones for web, sales, and mail.

Run the commands that create web, sales, and mail zones.

$ sudo firewall-cmd --permanent --new-zone=web --add-source=201.45.34.126
$ sudo firewall-cmd --permanent --new-zone=sales --add-source=201.45.15.48
$ sudo firewall-cmd --permanent --new-zone=mail --add-source=201.45.105.12


Set the zones to their designated interfaces.

Run the commands that set your eth interfaces to your zones.

$ sudo firewall-cmd --zone=public --change-interface=eth0
$ sudo firewall-cmd --zone=web --change-interface=eth1
$ sudo firewall-cmd --zone=sales --change-interface=eth2
$ sudo firewall-cmd --zone=mail --change-interface=eth3


Add services to the active zones.

Run the commands that add services to the public zone, the web zone, the sales zone, and the mail zone.

public:

$ sudo firewall-cmd --permanent --zone=public --add-service=http
$ sudo firewall-cmd --permanent --zone=public --add-service=https
$ sudo firewall-cmd --permanent --zone=public --add-service=pop3
$ sudo firewall-cmd --permanent --zone=public --add-service=smtp


web:

$ sudo firewall-cmd --permanent --zone=web --add-service=http


sales:

$ sudo firewall-cmd --permanent --zone=sales --add-service=https


mail:

$ sudo firewall-cmd --permanent --zone=mail --add-service=smtp
$ sudo firewall-cmd --permanent --zone=mail --add-service=pop3


What is the status of http, https, smtp and pop3?

HTTP is enabled on public and web
HTTPS is enabled on public and sales
SMTP is enabled on public and mail
POP3 is enabled on public and mail


Add your adversaries to the drop zone.

Run the command that will add all current and any future blacklisted IPs to the drop zone.

$ sudo firewall-cmd --zone=drop --add-source=10.208.56.23
$ sudo firewall-cmd --zone=drop --add-source=135.95.103.76
$ sudo firewall-cmd --zone=drop --add-source=76.34.169.118

Could also use “sudo firewall-cmd --new-zone=blacklist” to create a dedicated blacklist zone, then “sudo firewall-cmd --zone=blacklist --set-target=DROP” to create a specific drop protocol for it, then add IPs to that instead.


Make rules permanent, then reload them.

It's good practice to ensure that your firewalld installation remains nailed up and retains its services across reboots. This helps ensure that the network remains secure after unplanned outages such as power failures.

Run the command that reloads the firewalld configurations and writes it to memory:

$ sudo firewall-cmd --runtime-to-permanent

(if you use the --permanent tag as i did for most of this, you don’t need to do this and can do firewall-cmd --reload instead)


View active zones.

Now, provide truncated listings of all currently active zones. This is a good time to verify your zone settings.

Run the command that displays all zone services.

$ sudo firewall-cmd --get-active-zones


Block an IP address.

Use a rich-rule that blocks the IP address 138.138.0.3 on your public zone.

$ sudo firewall-cmd --zone=public --add-rich-rule=’rule family=”ipv4” source address=”138.138.0.3”


Block ping/ICMP requests.

Harden your network against ping scans by blocking icmp ehco replies.

Run the command that blocks pings and icmp requests in your public zone.

$ sudo firewall-cmd --zone=public --add-icmp-block=echo-reply --add-icmp-block=echo-request


Rule check.

Now that you've set up your brand new firewalld installation, it's time to verify that all of the settings have taken effect.

Run the command that lists all of the rule settings. Do one command at a time for each zone.

$ sudo firewall-cmd --zone=public --list-all
$ sudo firewall-cmd --zone=web --list-all
$ sudo firewall-cmd --zone=sales --list-all
$ sudo firewall-cmd --zone=mail --list-all
$ sudo firewall-cmd --zone=drop --list-all


Are all of the rules in place? If not, then go back and make the necessary modifications before checking again.

Congratulations! You have successfully configured and deployed a fully comprehensive firewalld installation.


Part 3: IDS, IPS, DiD and Firewalls

Now, you’ll work on another lab. Before you start, complete the following review questions.

IDS vs. IPS Systems

Name and define two ways an IDS connects to a network.

TAP - Splits inbound and outbound data onto independent streams, allowing the IDS to monitor traffic while it flows through the network.

  
SPAN - a mirror of all data gets copied to a separate port that is sent to the IDS, which stores the data for access and review.


Describe how an IPS connects to a network.

Inline - traffic flows through the IPS directly, which allows the IPS to both log and take action on potential threats. Also necessitates a hardware solution in order to avoid throttling network traffic.


What type of IDS compares patterns of traffic to predefined signatures and is unable to detect zero-day attacks?

Signature-Based. It’s kind of like a vaccine: it’s great for immunizing you against known threats, but novel viruses require time to update the list of antiviruses.


What type of IDS is beneficial for detecting all suspicious traffic that deviates from the well-known baseline and is excellent at detecting when an attacker probes or sweeps a network?

Anomaly-Based. This is more like a guard dog: it will bark at anything that looks suspicious or gets too close, but what it considers suspicious or too close is much broader than you may want without proper training.


Defense in Depth

For each of the following scenarios, provide the layer of defense in depth that applies:

A criminal hacker tailgates an employee through an exterior door into a secured facility, explaining that they forgot their badge at home.

Perimeter


A zero-day goes undetected by antivirus software.

Application


A criminal successfully gains access to HR’s database.

Data


A criminal hacker exploits a vulnerability within an operating system.

Host


A hacktivist organization successfully performs a DDoS attack, taking down a government website.

Network


Data is classified at the wrong classification level.

Data


A state-sponsored hacker group successfully firewalked an organization to produce a list of active services on an email server.

Network


Name one method of protecting data-at-rest from being readable on hard drive.

Encryption (permissions could also work if you don’t want me to say the same thing twice)


Name one method of protecting data-in-transit.

Also Encryption


What technology could provide law enforcement with the ability to track and recover a stolen laptop?

GPS - either with a transponder device (like tile or airtag), or by utilizing the geolocation data when the device connects to WiFi networks


How could you prevent an attacker from booting a stolen laptop using an external hard drive?

Administrative controls on the BIOS to prohibit booting from USB.


Firewall Architectures and Methodologies

Which type of firewall verifies the three-way TCP handshake? TCP handshake checks are designed to ensure that session packets are from legitimate sources.

Circuit-Level


Which type of firewall considers the connection as a whole? Meaning, instead of considering only individual packets, these firewalls consider whole streams of packets at one time.

Stateful Packet-Filtering


Which type of firewall intercepts all traffic prior to forwarding it to its final destination? In a sense, these firewalls act on behalf of the recipient by ensuring the traffic is safe prior to forwarding it.

Application/Proxy


Which type of firewall examines data within a packet as it progresses through a network interface by examining source and destination IP address, port number, and packet type—all without opening the packet to inspect its contents?

Stateless Packet-Filtering


Which type of firewall filters solely based on source and destination MAC address?

Mac Layer



Bonus Lab: “Green Eggs & SPAM”

In this activity, you will target spam, uncover its whereabouts, and attempt to discover the intent of the attacker.
 
You will assume the role of a junior security administrator working for the Department of Technology for the State of California.
 
As a junior administrator, your primary role is to perform the initial triage of alert data: the initial investigation and analysis followed by an escalation of high-priority alerts to senior incident handlers for further review.
 
You will work as part of a Computer and Incident Response Team (CIRT), responsible for compiling threat intelligence as part of your incident report.

Threat Intelligence Card

Note: Log in to the Security Onion VM, and use the following indicator of attack to complete this portion of the assignment. 


Locate the indicator of attack in Sguil based off of the following:

Source IP/port: 188.124.9.56:80
Destination address/port: 192.168.3.35:1035
Event message: ET TROJAN JS/Nemucod.M.gen downloading EXE payload

Answer the following questions:

What was the indicator of an attack? (Hint: What do the details reveal?)

Inside the transcript, there is an HTTP GET request for the file “40.exe”. Below it, the destination (our local IP) gives a HTTP 200 OK response, meaning the file was successfully downloaded.


What was the adversarial motivation (purpose of the attack)?

The attack appears to be preparation for continuing compromise, such as stealing confidential data or creating a zombie for a botnet.


Describe observations and indicators that may be related to the perpetrators of the intrusion. Categorize your insights according to the appropriate stage of the cyber kill chain, as structured in the following table:

TTP
Example
Findings
Reconnaissance
How did the attacker locate the victim?
It is most likely that the victim clicked on a malicious link, probably a banner ad on a website or a link placed into a spam email.
Weaponization
What was downloaded?
A trojan called Nemucod (sometimes JS.Nemucod) that acts as a downloader for further compromise and eventually C2
Delivery
How was it downloaded?
The attacker utilized an online uploading service (solaruploader.com) to download the file to the victim’s machine and launch it.
Exploitation
What does the exploit do?
Nemucod acts as a “trojan dropper”, which attempts to download and install additional malware to the victim’s computer after running.
Installation
How is the exploit installed?
When the payload is delivered, a javascript file is executed that creates a hidden program in the computer’s %TEMP% folder.
Command & Control (C2)
How does the attacker gain control of the remote machine?
With the trojan installed, additional malware such as keyloggers and backdoors can be utilized to gain control over the device. The trojan also attempts to establish a continuous connection with the C2 domain.
Actions on Objectives
What does the software that the attacker sent do to complete its tasks?
Apart from what has already been discussed, the malware suite ransomware has often been deployed by this trojan. Instead of directly corrupting the victim’s computer itself, Nemucod acts as a launching off point for separate attacks.


What are your recommended mitigation strategies?

all connections to the malicious IP and domain should be blocked to prevent further communications.
Additional network traffic scans should be conducted to determine if additional suspicious traffic has arrived at or been sent from the victim’s computer, to ensure no additional backdoors or compromised pathways exist.
Antivirus and antimalware should be run on the infected device, as well as any other devices that have recently interacted with it.
All temporary file locations should be purged, and any anomalous users or settings should be removed and restored to their previous states.
The infected computer should be checked for rootkits and bootkits.
If full eradication of the malicious software cannot be determined, attempt to restore the computer to a backup state prior to initial infection.
Finally, if no other option has succeeded, the computer should be completely reformatted and restored to initial settings.


List your third-party references.

https://www.malwaredomainlist.com/mdl.php?search=solaruploader.com&colsearch=All&quantity=50&inactive=on
https://en.wikipedia.org/wiki/Dropper_(malware)
https://encyclopedia.kaspersky.com/glossary/trojan-droppers/
https://www.welivesecurity.com/2016/08/09/nemucod-back-serving-ad-clicking-backdoor-instead-ransomware/
https://www.cisecurity.org/insights/blog/malware-analysis-report-nemucod-ransomware
https://www.microsoft.com/en-us/wdsi/threats/malware-encyclopedia-description?Name=JS/Nemucod
https://www.f-secure.com/v-descs/trojan-downloader_js_nemucod.shtml




© 2022 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.

