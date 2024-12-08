    Cybersecurity
Module 9 Challenge Submission File


In a Network Far, Far Away!

Make a copy of this document to work in, and then for each mission, add the solution below the prompt. Save and submit this completed file as your Challenge deliverable.


Mission 1

Mail servers for starwars.com:

starwars.com	mail exchanger = 10 aspmx2.googlemail.com.
starwars.com	mail exchanger = 10 aspmx3.googlemail.com.
starwars.com	mail exchanger = 5 alt2.aspmx.l.google.com.
starwars.com	mail exchanger = 5 alt1.aspx.l.google.com.
starwars.com	mail exchanger = 1 aspmx.l.google.com.


Explain why the Resistance isn’t receiving any emails:

There appear to be inconsistencies between the primary mail servers the Resistance is listing - asltx.[n].google.com (where [n] is the server number) - and the servers listed on their DNS records, which are aspmx[n].google.com. This could be a typo, or some change in how google, their email provider, labeled their email servers.


Suggested DNS corrections:

If it is a typo, the resistance should update the DNS record to replace aspmx with asltx (or update their own records to reflect the DNS record, if the typo is on their own systems).

If it is a change in email provider servers, they should communicate with google to update the connections they have with their MX servers.



Mission 2

Sender Policy Framework (SPF) of theforce.net:

theforce.net	text = "v=spf1 a mx a:mail.wise-advice.com mx:smtp.secureserver.net include:aspmx.googlemail.com ip4:104.156.250.80 ip4:45.63.15.159 ip4:45.63.4.215  ip4:104.207.135.156 ~all"



Explain why the Force’s emails are going to spam:

The new mail server IP address - 45.23.176.21 - is not in the list of approved IPv4 addresses in the SPF validation. This will lead to a failure of the SPF check when the message arrives, which is likely causing their spam filters to discount it as a potentially bogus message.


Suggested DNS corrections:

The Force should update its DNS TXT record to include the new mail server.



Mission 3

Document the CNAME records:

www.theforce.net	canonical name = theforce.net.

When looking for the cname for resistance.theforce.net:

** server can't find resistance.theforce.net: NXDOMAIN


Explain why the subpage resistance.theforce.net isn’t redirecting to theforce.net:

When an IP is requested over DNS for resistance.theforce.net, the response is NXDOMAIN - a non existent domain request. There has been no canonical name set to redirect the user to a particular IP and/or sublocation, and an error occurs.


Suggested DNS corrections:

As the subdomain should just redirect to the primary landing page, the resistance should add CNAME record that looks like the following:

resistance.theforce.net	canonical name = theforce.net.



Mission 4

Confirm the DNS records for princessleia.site:

princessleia.site	nameserver = ns26.domaincontrol.com.
princessleia.site	nameserver = ns25.domaincontrol.com.




Suggested DNS record corrections to prevent the issue from occurring again:

Update the DNS record to include the following information:
princessleia.site	nameserver = ns2.galaxybackup.com.



Mission 5

Document the shortest OSPF path from Batuu to Jedha:

OSPF path:

Batuu > D > C > E > F > J > I > L > Q > T > V > Jedha


OSPF path cost:

23

Also just for the sake of completion, I also checked what would happen if N was not excluded, and placed the image of that path below the image for the path requested by the mission, which is directly underneath this response.



Mission 6

Wireless key:

dictionary

For completion, here’s the whole aircrack-ng result:


                          KEY FOUND! [ dictionary ]


      Master Key     : 5D F9 20 B5 48 1E D7 05 38 DD 5F D0 24 23 D7 E2 
                       52 22 05 FE EE BB 97 4C AD 08 A5 2B 56 13 ED E2 

      Transient Key  : AF BB 3B 5A A8 69 05 13 73 5C 1C EC E0 A2 15 4A 
                       E0 99 6F A9 5B 21 1D A1 8E 85 FD 96 49 5F B4 97 
                       85 67 33 87 B9 DA 97 97 AA C7 82 8F 52 F0 EB C7 
                       05 04 C0 A3 7E 31 7C B3 DF 24 D5 25 85 EC EE 00 

      EAPOL HMAC     : 6D 45 F3 53 8E AD 8E CA 55 98 C2 60 EE FE 6F 51 





Host IP addresses and MAC addresses:

Sender MAC address:

00:13:ce:55:98:ef


Sender IP address:

172.16.0.101


Target MAC address:

00:0f:66:e3:e4:01


Target IP address:

172.16.0.1



Mission 7

Screenshot of results:

Awww that’s cute 😀

