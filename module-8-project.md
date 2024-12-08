    Cybersecurity
Module 8 Challenge Submission File


Networking Fundamentals: Rocking your Network

Make a copy of this document to work in. For each phase, add the solution below the prompt. Save and submit this completed file as your Challenge deliverable.


Phase 1: “I’d like to Teach the World to ping”

Command(s) used to run fping against the IP ranges:

fping -g 15.199.95.91/28 (Hollywood Database Servers)
fping -g 15.199.94.91/28 (Hollywood Web Server 1)
fping -g 203.0.113.32/28 (Hollywood Web Server 2)
fping -g 161.35.96.20/32 (Hollywood Applications Server 1)
fping -g 192.0.2.0/28 (Hollywood Applications Server 2)


Summarize the results of the fping command(s):

Hollywood Database IPs (from 155.199.95.81 to 155.199.95.94) are all unreachable.
Hollywood Web Server 1 IPs (from 155.199.94.81 to 155.199.94.94) are all unreachable.
Hollywood Web Server 2 IPs (from 203.0.113.33 to 203.0.113.45) are all unreachable.
Hollywood Application Server 1’s IP (161.35.96.20) is alive and reachable!
Hollywood Application Server 2 IPs (192.0.2.1 to 192.0.2.14) are all unreachable


List of IPs responding to echo requests:

Only one IP is currently responding to echo requests - 161.35.96.20


Explain which OSI layer(s) your findings involve:

echo/ICMP exists on Layer 3 - The Network layer. 


Mitigation recommendations (if needed):

As RockStar Corp has stated they do not want ANY server to respond to ICMP requests, they are advised to close or filter traffic sent across port 7 to the Application Server 1, as well as any other non-essential communication ports.



Phase 2: “Some SYN for Nothin’”

Which ports are open on the RockStar Corp server?

22 - ssh
25 - smtp
111 - rpcbind
135 - msrpc
139 - netbios-ssn
445 - microsoft-ds


Which OSI layer do SYN scans run on?

OSI layer:

Layer 4 - Transport


Explain how you determined which layer:

SYN (synchronize) is a TCP signal, which is one of the two primary protocols 


Mitigation suggestions (if needed):

Close these ports! Update the firewall! 



Phase 3: “I Feel a DNS Change Comin’ On”

Summarize your findings about why access to rollingstone.com is not working as expected from the RockStar Corp Hollywood office:

An unknown actor has edited the /etc/hosts to redirect rollingstone.com to the IP address 98.137.246.8


Command used to query Domain Name System records:

nslookup 98.137.246.8


Domain name findings:

The nslookup result shows that this IP address resolves to unknown.yahoo.com


Explain what OSI layer DNS runs on:

DNS runs on Layer 7, the Application layer


Mitigation suggestions (if needed):

Remove the potentially malicious DNS entry in /etc/hosts, and review sudoers access - /etc/hosts should only be writable as root, so this required root or sudo privileges.



Phase 4: “ShARP Dressed Man”

Name of file containing packets:

Packetcaptureinfo.txt (there’s also a .packetcaptureinfo.txt.swp file)


ARP findings identifying the hacker’s MAC address:
The hacker is using the MAC address 00:0c:29:1d:b3:b1, utilizing the local IP of 192.168.47.171 - in the Wireshark analysis, that source outputs an ARP request to identify the subnet IPs of 192.168.47.1 and 192.168.47.200, followed by an attempt at poisoning the ARP logs by broadcasting a followup ARP location answer that says the IP address ending in 200 is at the MAC address ending :b3:b - our original source MAC.


HTTP findings, including the message from the hacker:

The hacker connected to a website www.gottheblues.yolasite.com, who seem to be a competitor to RockStar Corp. They navigated to the contact-us page, then submitted the following information:
NAME: Mr. Hacker
EMAIL: Hacker@rockstarcorp.com
Message: Hi Got THe Blues Corp! This is a hacker that works at Rock Star Corp. Rock Star has left port 22, SSH open if you want to hack in. For 1 Milliion Dollars I will provide you the user and password!


Explain the OSI layers for HTTP and ARP.

Layer used for HTTP:

HTTP exists on layer 7 - the Application layer.


Layer used for ARP:

ARP exists on layer 2 - the Data Link Layer


Mitigation suggestions (if needed):

For ARP spoofing: There should be duplication filtering to avoid any poisoning of the ARP protocol, and/or detection tools in place to notice any duplicate ARP assignments. In more extreme circumstances, freezing the ARP cache may be necessary.

For HTTP Form findings: Close port 22 and/or CHANGE DEFAULT CREDENTIALS!!! Stop using default creds they’re BAD.




© 2023 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.
