# Cybersecurity Boot Camp
# Security 101 Challenge


Cybersecurity Threat Landscape

## Part I: Crowdstrike 2021 Global Threat Report 

### What was the dominant ransomware family that impacted the healthcare industry in 2020?

Maze (followed by Conti)

### Describe three different pandemic-related eCrime Phishing themes.

Exploiting people looking for information on disease tracking/testing/treatment - “Need a covid test for work? Click this totally not malicious link!”
Financial assistance & government stimulus packages - “Time to get your stimmy check!”
PPE Scams - “N90 Masks For Free, Click Here!”

### Which industry was targeted with the highest number of ransomware-associated data extortion operations?

Industrial/Engineering (229 incidents) followed by manufacturing (228)

### What is WICKED PANDA? Where do they originate from?

A hacker organization (also known as APT41) with ties to China and the Chinese Ministry of State Security

### Which ransomware actor was the first observed using data extortion in a ransomware campaign?

Outlaw Spider

### What is an access broker? 

An individual or organization that sells access to compromised networks

### Explain a credential-based attack.

Using stolen credentials (like those found from data breaches) to gain access to a company or organization’s servers, bypassing security, and stealing sensitive data.

### Who is credited for the heavy adoption of data extortion in ransomware campaigns?

Twisted spider

### What is a DLS?

Dedicated Leak Site - a website where hacking organizations can auction off or otherwise distribute sensitive data they’ve stolen

### According to Crowdstrike Falcon OverWatch, what percentage of intrusions came from eCrime intrusions in 2020? 

79%

### Who was the most reported criminal adversary of 2020? 

Wizard Spider

### Explain how SPRITE SPIDER and CARBON SPIDER impacted virtualization infrastructures.

They targeted a series of ransomware on linux ESXi hosts, acquired admin credentials, and encrypting the ESXi server to pwn multiple virtual machines in one strike, rather than having to deploy ransomware on each individual VM.

### What role does an Enabler play in an eCrime ecosystem?

They let criminals who might not otherwise participate in eCrime do so by:
Running malware-as-a-service
Provide delivery mechanisms for malware
Provide network exploits
Overall, they sell initial access to vulnerable organizations.

### What are the three parts of the eCrime ecosystem that CrowdStrike highlighted in their report?

Services, Distribution, and Monetization

### What is the name of the malicious code used to exploit a vulnerability in the SolarWinds Orion IT management software?

SUNBURST


## Part 2: Akamai Security Year in Review 2020

### What was the most vulnerable and targeted element of the gaming industry between October 2019 to September 2020? 

The players - specifically, their user credentials. (50% of polled compromised!)

### From October 2019 to September 2020, which month did the financial services industry have the most daily web application attacks? 

December 2019 (though this was due to a single spike on Dec 09)

### What percentage of phishing kits monitored by Akamai were active for only 20 days or less? 

60%

### What is credential stuffing? 

Using login credentials from something like a breach or leak to try and break into a user’s account on an unrelated service.

### Approximately how many of the gaming industry players have experienced their accounts being compromised?  How many of them are worried about it?

Over 50% have been compromised, but only 20% are worried! 

### What is a three-question quiz phishing attack?

A scam that promises rewards (like a gift card) if victims answer a questionnaire that involves answering three questions about their personal information - making it easier for them to fall victim to password reset attempts or at worst identity theft

### Explain how Prolexic Routed defends organizations against DDoS attacks.

It’s basically a firewall - network traffic goes through the data scrubbing centers, and if the traffic is safe it’s allowed through. I assume Cloudflare operates on a similar principle.

### What day between October 2019 to September 2020 had the highest Daily Logins associated with Daily Credential Abuse Attempts? 

August 17, 2020 - over 365 million!

### What day between October 2019 to September 2020 had the highest gaming attacks associated with Daily Web Application Attacks? 

July 11, 2020 - 14.6 million!

### What day between October 2019 to September 2020 had the highest media attacks associated with Daily Web Application Attacks?

August 20, 2020 - 5.1 million!


## Part 3: Verizon Data Breaches Investigation Report

### What is the difference between an incident and a breach? 

A breach is a subset of an incident - An incident is a security event that compromises the asset, while a breach is an incident that results in confirmed disclosure of the data to an unauthorized party.

### What percentage of breaches were perpetrated by outside actors? What percentage were perpetrated by internal actors? 

Over 65% were perpetrated by outside actors, rising to around 80% in 2020. Internal actors were responsible for around 30%, dropping to just over 20% in 2020

### What percentage of breaches were perpetrated by organized crime? 

80%

### What percentage of breaches were financially motivated? 

Well over 75%

### Define the following (additional research may be required outside of the report): 

Denial of service: Disabling a machine or network through traffic-flooding or forcing a crash to remove accessibility from users.

Command control: a server controlled by an attacker, to send commands to systems compromised by malware and to receive data stolen from a target network. (a shell sherpa?)

Backdoor: an undocumented method for gaining access to a system. 

Keylogger: software or hardware that records every keypress that a user types into a device.

### What remains one of the most sought-after data types for hackers? 

Credentials (which makes sense - it’s access that involves the least amount of work)

### What was the percentage of breaches involving phishing?

36%