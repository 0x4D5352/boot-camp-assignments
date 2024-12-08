    Cybersecurity
21.3 The Final Report












Case Report 
National Gallery DC
Tracy’s iPhone [2012-07-15-National-Gallery]





















Table of Contents



Case Report
National Gallery DC
Tracy’s iPhone [2012-07-15-National-Gallery]
Table of Contents
Executive Summary
Equipment and Tools
Details of Tracy’s iPhone
Evidence to Establish Personas
Evidence relating to theft of valuable stamps
Evidence relating to defacement of museum art
Plot Timeline
Conclusion
Appendix A: Correspondence Evidence
Appendix B: WiFi and GPS Location Information
Appendix C: Photographic Records of Evidence
Appendix D: Recovered Evidence
Executive Summary

On January 21, 2016, Digitech Inc. was called in to assist the National Gallery, Washington D.C. (NGDC) case involving the conspiracy associated with the theft of valuable stamps and defacing of museums are at the NGDC. 

Tracy is a suspect in the aforementioned conspiracy. 
As part of the investigation, Tracy’s iPhone was taken into custody. 
Digitech, Inc. was tasked with investigating evidence relevant to the aforementioned conspiracy.

As described fully in the report, Digitech, Inc. made the following findings. 

Digitech’s analyst believes that financial duress and family conflict contributed to the circumstances described. A trail of messages between Tracy and her daughter, Terry, in the days before, during, and after the vandalism plot took place indicate a strained relationship -  including arguments and ghosted messages. Concurrently with these events, Tracy coordinated with Pat via phone call, SMS, and email in order to plan the theft, and coordinated with Carry via phone call, SMS, and in-person meetings in order to plan what Tracy appeared to believe was a flash mob. 

Additional analysis of Tracy’s iPhone contents uncovered evidence of Pat blackmailing a separate individual named King into assisting with the heist, as well as evidence of Tracy documenting the stamps they planned to steal as well as insurance information regarding the stamps. Upon receiving a list of supplies from King via Pat, Tracy’s GPS coordinates were tracked across multiple locations around the greater Arlington, Virginia area within a period of 15 minutes, including convenience stores like CVS.

Finally, SMS conversations between Tracy and Carry the day before the vandalism indicate that Tracy received a tablet from Carry, which she placed inside the NGDC. The following day, she further confirmed her involvement by inquiring about the status of the flash mob.


Equipment and Tools

A forensic image of Tracy’s iPhone was made using the EnCase forensic imaging software, and imported into a Kali Linux virtual machine for further processing. The image was analyzed with the Autopsy digital forensics tool, and copies of databases were analyzed using sqlitebrowser. Finally, digital copies of iPhone contents were securely transferred via SSH to an analyst’s Mac computer where further analysis was performed using the Python scripting  language, as well as encrypted archives opened using John the Ripper. 

Database records hosted on Google Sheets, and can be viewed at the following: Tracy Timeline

Details of Tracy’s iPhone

Case Name: 2012-07-15-National-Gallery		Case #: 1EZ215-P


Details of Tracy’s iPhone

Name
Findings
Location in iPhone image file
Model
iPhone 1 or 2 (iPhone 3G)
/mobile/Library/logs/AppleSupport/general.log
Host Name
Tracy Sumtwelve’s iPhone
/logs/lockdownd.log.1
OS Version
iPhone OS 4.2.1 (8C148)
/mobile/Library/logs/AppleSupport/general.log
Install Time
2012/06/06 12:03:28 UTC-0700 (19:03:28 UTC)
/mobile/Library/logs/AppleSupport/general.log
User Email
tracysumtwelve@gmail.com AND/OR coralbluetwo@hotmail.com
vol5/mobile/Library/Mail
Phone Number
+1 (703) 340-9661
/logs/lockdownd.log.1
Serial Number
860044B2Y7H
/mobile/Library/logs/AppleSupport/general.log
ICCID
89014103255195342366
/logs/lockdownd.log.1
IMEI
012021003735398
/root/Library/Lockdown/activation_records/wildcard_record.plist
MD5 Hash
34c4888f095dc3241330462923f6fea5
tracy-phone-2012-07-15-final.E01
SHA256 Hash
71aed05a86a753dec4ef4033ed7f52d6577ccb534ca0d1e83ffd27683e621607
tracy-phone-2012-07-15-final.E01

Evidence to Establish Personas


This section establishes aliases, phone numbers, emails addresses associated with each person, and relationships between each individual. 

Tracy Sumtwelve (AKA Coral): 
	Phone Number: 	(703) 340-9961
	Personal Email:	tracysumtwelve@gmail.com
	Work Email: 		tracy.sumtwelve@nationalgallerydc.org
	Alias Email:		coralbluetwo@hotmail.com
	Relationship:		Accused

Pat Tee (AKA Perry): 
	Phone Number: 	(571) 308-3236
	Personal Email:	patsumtwelve@gmail.com
	Alias Email:		perrypatsum@yahoo.com
	Relationship: 		Brother, Co-Conspirator

Terry Sumtwelve:
	Phone Number:	(703) 829-6071	 
	Email:			N/A
	Relationship:		Daughter

Joe Sumtwelve: 
	Phone Number: 	N/A
	Email:			N/A
	Relationship: 		Ex-Husband

Carry:
	Phone Number:	(202) 725-2124
	Email:			N/A
	Relationship: 		Co-Conspirator
	

Tracy’s information was discovered through her iPhone, which had the three linked email accounts and the attached phone. Inside her address book were contact details for Pat and Carry. Email sent between Pat and Tracy using pseudonyms were connected to email and SMS conversations using both aliases and contact emails. Tracy’s contact information was found via SMS conversations. Joe’s contact information was not available.
Evidence relating to theft of valuable stamps

This sub-section provides details regarding the evidence found as it relates to the theft of valuable stamps. 

Three crucial pieces of evidence can be connected to the theft - First, the email and SMS correspondences between Pat, Tracy, and King [See Appendix A, Articles 10-13, 16, 18-21]. These messages, through real names and pseudonyms, connect the surrounding circumstances to Tracy’s request for her brother to assist, to Pat’s blackmailing of King, and Tracy acquiring the resources. While circumstantial, GPS coordinates following the delivery of required materials for the heist to Tracy track her movements in a way consistent with the acquisition of said resources [See Appendix B, Articles 34-40].

Second, an email from one of Tracy’s emails to another containing an encrypted archive of insurance documents relating to the stamps [See Appendix A, Article 17, and Appendix C]. Combined with the final piece of evidence - Tracy’s iPhone photos containing pictures in and around the National Gallery, including multiple photographs of the Gallery’s stamp collection [See Appendix C] - these demonstrate a degree of premeditation with regards to the value and location of the stamps.

Evidence relating to defacement of museum art

This sub-section provides details regarding the evidence found as it relates to the defacement of museum art. 

The first piece of evidence relating to the defacing of NGDC property is circumstantial, but SMS records build a relationship between Tracy and Carry [See Appendix A, Articles 8-9, 14-15]. The second piece of evidence is more concrete - SMS records on July 11 and 12 [See Appendix A, Articles 26-28] indicate that Tracy met up with Carry outside the NGDC, acquired a tablet computer from Carry, brought the tablet into the NGDC, and later corresponded with Carry about the status of what was referred to as a “flashmob[sic]”. While not demonstrating foreknowledge of the vandalism, this clearly illustrates Tracy’s connection and involvement with the act. 

Plot Timeline
NOTE: All timestamps are converted to UTC to normalize time zone differences.

Date/Time (UTC)
Event
Source
June 12




21:25:04
Pat messages Tracy asking about her weekend plans.
SMS
June 13




17:30:28
Terry messages Tracy about dinner w/ her father.
SMS
18:30:28
Tracy replies to Pat saying she has no plans.
SMS
18:33:46
Tracy replies to Terry acknowledging the plans.
SMS
19:01 - 19:04
Tracy's location is tracked in Downtown Arlington Area, including The Sycamore School
GPS (Cell)
June 19




12:38:59
Using pseudonyms, Pat (as Perry) emails Tracy (as Coral) an mp3 file labeled "crazydave1.mp3, telling her to check it out. Inside the audio file are drum recordings, with a robot voice instructing Tracy how to install VirtualBox on her mac computer, and that it is important for "Project Big Lived"
Email
June 23 - July 2
Data logged, but no notable activity during this period.
GPS (Cell/CellLocal)
July 3




13:41:51
Tracy messages Terry about lack of funding for Prufrock private school.
SMS
13:42:42
Tracy's location is tracked in the National Gallery Garden
GPS (CellLocal)
14:04:32
Terry replies angrily about the possibility of changing schools
SMS
July 5




16:32:46
Tracy's location is tracked in the National Gallery Backlot
GPS (CellLocal)
18:18:23
Carry messages Tracy about meeting at Bubba's Grill @ 1 PM
SMS
18:20:26
Tracy replies to Carry confirming the meeting.
SMS
July 6




15:02:19
Tracy messages Pat requesting a phone call.
SMS
15:08:37
Pat replies to Tracy saying he's busy, asking to postpone the call.
SMS
15:11:54
Tracy replies to Pat saying she cannot wait and that it is important.
SMS
15:13:31
Pat replies to Tracy, confirming a phone call 5 minutes after the message.
SMS
16:27:16
Carry messages Tracy, saying she has a table
SMS
16:27:50
Tracy replies to Carry, confirming that she will arrive soon.
SMS
July 7




15:59:31
Pat emails King, CCing Tracy, blackmailing King into assisting in robbing the National Gallery.
Email
July 8




16:03 - 17:02
Tracy takes photos in and around the National Gallery, including multiple photos of stamps.
iPhone Photos
16:34/16:39
Tracy's location is tracked in a separate location via WiFi GPS coordinates
GPS(WiFi)
July 9




14:47:53
Tracy emails herself two files - a zip file named "documents" and a folder named "docs" that contains 3 PDFs, each detailing insurance information on stamps hosted at the National Gallery
Email
July 10




15:19:00
King emails Pat, agreeing to the job and attaching a document with required tools for the heist.
Email
15:24:57
Pat forwards King's email, attachment included, to Tracy.
Email
15:26:19
Pat messages Tracy informing her about the forwarded email.
SMS
15:58:04
Tracy replies to Pat, acknowledging the information.
SMS
16:31 - 16:47
Tracy's location is tracked in various locations throughout the greater Arlington area. NOTE: During this time period, a message likely containing an image was sent to Pat, but is not available in the data provided.
GPS (WiFi)
17:18:38
Tracy messages Terry, asking if she would like to get lunch together.
SMS
18:19:24
Tracy messages Terry, informing her she has returned to work.
SMS
18:58:24
Terry replies to Tracy, informing her that she's busy and might be busy the whole weekend.
SMS
July 11




12:41:45
Carry messages Tracy, informing about her impending arrival.
SMS
12:49:08
Tracy replies, saying to meet out front and that she will take the tablet inside
SMS
July 12




17:06:45
Tracy messages Carry: "How's the flashmob going"
SMS
July 13




1:02:10
Terry messages Tracy, asking to go to her Father's for the weekend.
SMS




Conclusion

Evidence found on Tracy’s iPhone indicated the following: 

Tracy’s relationship with her daughter and ex-husband are strained.
Tracy’s financial situation is unstable, placing her under additional duress.
Tracy and Pat will communicate with each other using the respective aliases of Coral and Perry.
Tracy has a friendly relationship with Carry, and was willing to participate in her actions.
Tracy collected multiple pieces of information regarding the stamps held at NGDC, including insurance documents and photographs.
Pat is willing to commit additional crimes in order to achieve his goals.


Appendix A: Correspondence Evidence

This subsection will provide both the email and SMS correspondence evidence. 

NOTE: All timestamps are converted to UTC to normalize time zone differences.

Master Timeline of NGDC
Artifact #
Timestamp
Header Information
Key Information 
Evidence Location
1
2012-06-12 21:25:04
FROM: Pat
TO: Tracy
What are you up to this weekend?
/mobile/Library/SMS
2
2012-06-13 17:30:28
FROM: Terry
TO: Tracy
I'm going out with dad after school for pizza! Thought I'd let you know if you planned to cook.
/mobile/Library/SMS
3
2012-06-13 18:30:38
FROM: Tracy
TO: Pat
I don't have any big plans. How about you?
/mobile/Library/SMS
4
2012-06-13 18:33:46
FROM: Tracy
TO: Terry
Ok, sounds good.
/mobile/Library/SMS
5
2012-06-19 21:38:59
FROM: Pat (Perry)
TO: Tracy (Coral)
Subject: Crazydave by the VMs
Hey Coral, Just got your email. That took longer than expected! Oh well! You've got to check out this new song by the VMs. I love the base. Tell me what you think! Perry

[NOTE: Attached "crazydave1.mp3", an audio file containing 79 seconds of drums, followed by a 70 second robotic audio clip, followed by approximated 2.5 minutes of more drums. The robotic audio clip discusses installing VirtualBox on a Mac while other people are speaking in the background. The robot discusses "Project Big Lived", and says it's from "Perry".]
/mobile/Library/Mail/POP-coralbluetwo@hotmail.com@pop3.live.com/INBOX.mbox/Messages/3896FC6F-A083-4D39-B0A2-CE68368D44CA


6
2012-07-03 13:41:51
FROM: Tracy
TO: Terry
Hey honey. I'm not sure if we can afford Prufrock anymore... What do you think about maybe switching to someplace else?
/mobile/Library/SMS
7
2012-07-03 14:04:32
FROM: Terry
TO: Tracy
moving schools at this point would be the worst! i would rather live with dad and stay at prufrock then change schools :(
/mobile/Library/SMS
8
2012-07-05 18:18:23
FROM: Carry
TO: Tracy
Sounds good let's shoot for one àt Bubba s grill
/mobile/Library/SMS
9
2012-07-05 18:20:26
FROM: Tracy
TO: Carry
Okay that sounds great. See you there
/mobile/Library/SMS
10
2012-07-06 15:02:19
FROM: Tracy
TO: Pat
Hey can you give me a call
/mobile/Library/SMS
11
2012-07-06 15:08:37
FROM: Pat
TO: Tracy
Sis I'm really busy can we can do this later
/mobile/Library/SMS
12
2012-07-06 15:11:54
FROM: Tracy
TO: Pat


No pat this is important I need you to call me soon
/mobile/Library/SMS
13
2012-07-06 15:13:31
FROM: Pat
TO: Tracy
Ok ok I'll call in 5
/mobile/Library/SMS
14
2012-07-06 16:27:16
FROM: Carry
TO: Tracy
I have a table inside
/mobile/Library/SMS
15
2012-07-06 16:27:50
FROM: Tracy
TO: Carry
Okay brt
/mobile/Library/SMS
16
2012-07-07 15:59:31
FROM: Pat
TO: King
Subject: can’t pass up
King, Long time no see...I have a juicy proposition for you. Two weeks from now, me and my associates are planning a heist at the national gallery. Although, we need a helping hand. I know that you are on parole right now and are probably hesitant to participate. Me and your parole officer go years back. He is a very strict fellow. If he were to find out that you were dealing drugs and shooting dope in your veins every night, i feel he wouldn’t be too happy. It’s very easy for a person to phone the feds an anonymous tip that you are on drugs and the location of your stash. All they have to do is give you a drug test and since you're on parole, the feds don’t need a search warrant. Well hit me up. You know where to find me. 
[NOTE: CC'd Tracy (coralbluetwo@hotmail.com)]
/mobile/Library/Mail/POP-coralbluetwo@hotmail.com@pop3.live.com/INBOX.mbox/Messages/9F0508B8-04FB-490E-A7F0-3E23B0E7C59B



17
2012-07-09 14:47:53
FROM: Tracy
TO: Tracy
Subject: things
somethings
[NOTE: Attached "documents.zip" and "docs". "docs" contains PDF files detailing insurance information regarding stamps hosted at the National Gallery]
/mobile/Library/Mail/POP-coralbluetwo@hotmail.com@pop3.live.com/INBOX.mbox/Messages/8A3BD06F-CDB1-4453-9C69-77E06823F2AE


18
2012-07-10 15:19:00
FROM: King
TO: Pat
Subject: re: can’t pass up
You're too kind... I got you brotha. I need some tools in order to do this job for you. Here are some requirements that i will need:

see attachment
[NOTE: Attached "needs.txt"]
/mobile/Library/Mail/POP-coralbluetwo@hotmail.com@pop3.live.com/INBOX.mbox/Messages/9F0508B8-04FB-490E-A7F0-3E23B0E7C59B


19
2012-07-10 15:24:57
FROM: Pat
TO: Tracy
Subject: fwd: can’t pass up
this is what we need to get for the guy thats going to make our job happen
[NOTE: Attached "needs.txt"]
/mobile/Library/Mail/POP-coralbluetwo@hotmail.com@pop3.live.com/INBOX.mbox/Messages/9F0508B8-04FB-490E-A7F0-3E23B0E7C59B


20
2012-07-10 15:26:19
FROM: Pat
TO: Tracy
hey sis yo friend coral got a email the attachment needs to be changed to pdf let her know
/mobile/Library/SMS
21
2012-07-10 15:58:04
FROM: Tracy
TO: Pat
Sure thing I'll get on it
/mobile/Library/SMS
22
2012-07-10 16:37:09
FROM:  Tracy/Pat
TO:  Tracy/Pat
[Analyst's Notes = This appears to be some sort of multimedia message - an image or video, likely sent to or from Pat]
/mobile/Library/SMS
23
2012-07-10 17:18:38
FROM: Tracy
TO: Terry
Going to lunch. You want to go????!
/mobile/Library/SMS
24
2012-07-10 18:19:24
FROM: Tracy
TO: Terry
Back at work
/mobile/Library/SMS
25
2012-07-10 18:58:24
FROM: Terry
TO: Tracy
I'm busy. Maybe this weekend if dad isn't busy
/mobile/Library/SMS
26
2012-07-11 12:41:45
FROM: Carry
TO: Tracy
I'm almost there where should I meet you?
/mobile/Library/SMS
27
2012-07-11 12:49:08
FROM: Tracy
TO: Carry
Just meet me out front, I'll take the tablet in.
/mobile/Library/SMS
28
2012-07-12 17:06:45
FROM: Tracy
TO: Carry
How's the flashmob going
/mobile/Library/SMS
29
2012-07-13 1:02:10
FROM: Terry
TO: Tracy
I really want to go to Dad's this weekend. He said he'll take me shopping for school
/mobile/Library/SMS





Appendix B: WiFi and GPS Location Information
Relevant Map data has been uploaded at the following URL: https://www.google.com/maps/d/u/0/edit?mid=1GSFDwTSkZxJLCbQZtIxlIlr4I9SILRE&usp=sharing 
NOTE: All timestamps are converted to UTC to normalize time zone differences. Map data at end of photographic record.

	Location Information 
Artifact #
Timestamp
Data Source
Location
1
2012-06-13 19:01:21
GPS - Cell Location
Residential/Suburban Street
2
2012-06-13 19:01:22
GPS - Cell Location
The Sycamore School
3
2012-06-13 19:04:03
GPS - Cell Location
Residential/Empty Lot
4
2012-06-23 17:12:16
GPS - Cell Location
Army Navy Country Club/Golf Course
5
2012-07-02 16:19:23
GPS - Cell Location
Residential/Townhouses
6
2012-07-02 16:19:24
GPS - CellLocal Location
Downtown/Condominium - Anomaly
7
2012-07-03 13:42:42
GPS - CellLocal Location
National Gallery Garden
8
2012-07-05 16:32:46
GPS - CellLocal Location
National Gallery Backlot
9
2012-07-05 16:32:47
GPS - CellLocal Location
South Alexandria - Anomaly
10
2012-07-08 16:33:36
IMG_0042.JPG
Outdoors - Near National Gallery
11
2012-07-08 16:34:31
IMG_0043.JPG
Outdoors - Near National Gallery
12
2012-07-08 16:34:40
GPS - WiFi Location
Virginia Tech Research Center
13
2012-07-08 16:34:50
IMG_0044.JPG
Outdoors - Near National Gallery
14
2012-07-08 16:35:50
IMG_0045.JPG
Outdoors - Near National Gallery
15
2012-07-08 16:36:30
IMG_0046.JPG
Outdoors - Near National Gallery
16
2012-07-08 16:37:16
IMG_0047.JPG
Outdoors - Near National Gallery
17
2012-07-08 16:37:37
IMG_0048.JPG
Outdoors - Near National Gallery
18
2012-07-08 16:39:10
GPS - WiFi Location
Parking Garage (Near VTRC)
19
2012-07-08 16:41:41
IMG_0049.JPG
Indoors - National Gallery
20
2012-07-08 16:41:53
IMG_0050.JPG
Indoors - National Gallery
21
2012-07-08 16:42:03
IMG_0051.JPG
Indoors - National Gallery
22
2012-07-08 16:49:25
IMG_0054.JPG
Indoors - National Gallery
23
2012-07-08 16:49:37
IMG_0055.JPG
Indoors - National Gallery
24
2012-07-08 16:49:49
IMG_0056.JPG
Indoors - National Gallery
25
2012-07-08 16:50:07
IMG_0057.JPG
Indoors - National Gallery
26
2012-07-08 16:50:20
IMG_0058.JPG
Indoors - National Gallery
27
2012-07-08 16:51:44
IMG_0064.JPG
Indoors - National Gallery
28
2012-07-08 16:59:55
IMG_0065.JPG
Indoors - National Gallery
29
2012-07-08 17:00:01
IMG_0066.JPG
Indoors - National Gallery
30
2012-07-08 17:00:07
IMG_0067.JPG
Indoors - National Gallery
31
2012-07-08 17:00:12
IMG_0068.JPG
Indoors - National Gallery
32
2012-07-08 17:00:23
IMG_0069.JPG
Indoors - National Gallery
33
2012-07-08 17:02:23
IMG_0070.JPG
Indoors - National Gallery
34
2012-07-10 16:31:10
GPS - WiFi Location
Shopping Plaza (Near VTRC)
35
2012-07-10 16:31:12
GPS - WiFi Location
Virginia Tech Research Center
36
2012-07-10 16:31:12
GPS - WiFi Location
Westin Arlington (Near VTRC)
37
2012-07-10 16:44:59
GPS - WiFi Location
Residential/Suburban Street
38
2012-07-10 16:45:01
GPS - WiFi Location
Hotel Parking Lot Near Last Location
39
2012-07-10 16:46:29
GPS - WiFi Location
Residential/Commercial Areas
40
2012-07-10 16:47:12
GPS - WiFi Location
Outlet Mall Near Last Location



Appendix C: Photographic Records of Evidence




Appendix D: Recovered Evidence




