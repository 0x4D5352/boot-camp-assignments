    Cybersecurity
Project 1 Technical Brief


Make a copy of this document before you begin. Place your answers below 
each question. This completed document will be your deliverable for Project 1. Submit it through Canvas when you’re finished with the project at the end of the week.


Your Web Application

Enter the URL for the web application that you created:

https://mussar.io/


Paste screenshots of your website created (Be sure to include your blog posts):








Day 1 Questions

General Questions

What option did you select for your domain (Azure free domain,  GoDaddy domain)?

I used Google Domains instead of GoDaddy


What is your domain name?

mussar.io/ - Mussar is my online handle, and the .io top level domain is a nice tech-y domain


Networking Questions

What is the IP address of your webpage?

20.119.0.23


What is the location (city, state, country) of your IP address?

Tappahannock, Virginia


Run a DNS lookup on your website. What does the NS record show?

Server:		2600:1700:19e2:180::1
Address:	2600:1700:19e2:180::1#53
Non-authoritative answer:
Name:	mussar.io
Address: 20.119.0.23


Web Development Questions

When creating your web app, you selected a runtime stack.  What was it? Does it work on the front end or the back end? 

PHP - it’s a back end application; the PHP generates the web pages for us.


Inside the /var/www/html directory, there was another directory called assets. Explain what was inside that directory.

Two folders - ./css and ./images. CSS is the cascading style sheet, which allows for design and formatting of webpages to look all nice and pretty, and images is where the pictures such as the background can be stored.


Consider your response to the above question. Does this work with the front end or back end?

This is the front end stuff - what the client sees!



Day 2 Questions

Cloud Questions

What is a cloud tenant?

Someone who rents space in a cloud infrastructure. Right now, I’m a cloud tenant hosting my blog on the Azure cloud.


Why would an access policy be important on a key vault?

The key vault itself holds all the keys for the network, service, or what have you. Someone who has the ability to access all of those can do some major damage. Conversely, restricting access for users to only the services they need to use will lower the amount of complexity required to maintain access.


Within the key vault, what are the differences between keys, secrets, and certificates?

Keys are the same thing we’ve been using with ssh-keygen - a cryptographic key pair that allows us to digitally sign information, as well as encrypt the information.

Secrets, according to the official microsoft documentation (https://learn.microsoft.com/en-us/azure/key-vault/secrets/about-secrets) is a way to store “generic secrets, such as passwords and database connection strings”. This could also work for API Keys, and other sensitive information that can be stored as a line of text.

Certificates are forms of identification that allow us to have a trusted third party verify that we are who we say we are. According to the official documentation, they’re “built on top of keys and secrets and add an automated renewal feature.” 


Cryptography Questions

What are the advantages of a self-signed certificate?

No overhead, helps guarantee encryption, works great for an intranet where you just want the benefits of HTTPS


What are the disadvantages of a self-signed certificate?

You don’t get any identity validation, so no one can prove who you are who you say you are. As a result, lots of browsers will block users from visiting your site without workarounds.


What is a wildcard certificate?

Wildcard certificates are similar to wildcards in the terminal - they match up to anything that contains the rest of the string. In this instance, it means the certificate applies to all subdomains (as per https://www.techtarget.com/searchsecurity/definition/wildcard-certificate) for a given domain - e.g *.website.com. 


When binding a certificate to your website, Azure only provides TLS versions 1.0, 1.1, and 1.2.  Explain why SSL 3.0 isn’t provided.

Well, now it no longer offers any TLS version besides 1.2, but SSL 3.0 is vulnerable to the POODLE vulnerability: https://en.wikipedia.org/wiki/POODLE


After completing the Day 2 activities, view your SSL certificate and answer the following questions:

Is your browser returning an error for your SSL certificate? Why or why not?

No error! I have a valid certificate signed from GeoTrust Global with a root CA from DigiCert Global! All the proper information has been validated.


What is the validity of your certificate (date range)?

March 28, 2023 at 19:00:00 CDT - September 29, 2023 at 18:59:59 CDT


Do you have an intermediate certificate? If so, what is it?

Yes! GeoTrust Global TLS RSA4096 SHA256 2022 CA1


Do you have a root certificate? If so, what is it?

Yes! DigitCert Global Root CA


Does your browser have the root certificate in its root store?

Yes! On Mac, you can go to the Keychain Access application. Under the System Roots keychain, you can find that root and all the other root certs Apple considers valid under the “Certificates” tab


List one other root CA in your browser’s root store.

Starfield Class 2 Certification Authority (cause they sound like something from a sci-fi show)



Day 3 Questions

Cloud Security Questions 

What are the similarities and differences between Azure Web Application Gateway and Azure Front Door?

Similarities:
Both work as a way to help protect your web application by sitting in between it and incoming traffic.
Both utilize load balancing and firewalls to filter traffic.
Both exist on Layer 7, the Application Layer.
Differences:
The gateway is a way to filter content traveling within a network, like turnstiles at a subway station.
The front door is acting like the front door of your own house - it controls access from the outside.


A feature of the Web Application Gateway and Front Door is “SSL Offloading.” What is SSL offloading? What are its benefits?

SSL offloading takes an encrypted stream of data (like HTTPS traffic) and routes it through an intermediary server that communicates with the actual web application using unencrypted traffic. This means that any communications are only encrypted or decrypted once for each party, and helps protect against malicious payloads hitting the web application via encrypted traffic.


What OSI layer does a WAF work on?

7 (Application)


Select one of the WAF managed rules (e.g., directory traversal, SQL injection, etc.), and define it.

“JSFuck / Heiroglyphy obfuscation detected” - JSFuck and Heiroglyphy are code obfuscation tools that can mask javascript code by turning it into symbols like parentheses and brackets. This rule is searching for instances of these obfuscated scripts in order to prevent a potentially malicious code execution.


Consider the rule that you selected. Could your website (as it is currently designed) be impacted by this vulnerability if Front Door wasn’t enabled? Why or why not?

Right now, there’s no place for malicious code to interact with my blog. Running code client side shouldn’t have any effect on the server, so there’s no need to obfuscate it there. I don’t think it would affect my blog if this was disabled. 


Hypothetically, say that you create a custom WAF rule to block all traffic from Canada. Does that mean that anyone who resides in Canada would not be able to access your website? Why or why not? 

If they are using their ISP-designated IP address, they would not be able to. However, if they use a VPN, they could spoof their location to be in an allowed location and have no trouble connecting.


Include screenshots below to demonstrate that your web app has the following:

Azure Front Door enabled




A WAF custom rule





Disclaimer on Future Charges 

Please type “YES” after one of the following options:

Maintaining website after project conclusion: I am aware that I am responsible for any charges that I incur by maintaining my website. I have reviewed the guidance for minimizing costs and monitoring Azure charges.

YES

Disabling website after project conclusion: I am aware that I am responsible for deleting all of my project resources as soon as I have gathered all of my web application screen shots and completed this document.



© 2022 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.

