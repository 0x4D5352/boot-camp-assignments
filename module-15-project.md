    Cybersecurity
Module 15 Challenge Submission File

Testing Web Applications for Vulnerabilities

Make a copy of this document to work in, and then respond to each question below the prompt. Save and submit this completed file as your Challenge deliverable.

Web Application 1: Your Wish is My Command Injection

Provide a screenshot confirming that you successfully completed this exploit:




Write two or three sentences outlining mitigation strategies for this vulnerability: 

The logic for passing the IP address can be safer with input validation. A server side filter that uses a regular expression to filter out anything that isn’t an IP address could work, or splitting the input string on the periods and grabbing the first four items. 


Web Application 2: A Brute Force to Be Reckoned With

Provide a screenshot confirming that you successfully completed this exploit:




Write two or three sentences outlining mitigation strategies for this vulnerability: 

The biggest concern here is that I was able to perform all 100 login attempts with no inhibition. Requiring a captcha after a certain number of login attempts would be minimally invasive on legitimate users, but paralyze most if not all automated attacks. An even better solution would be to switch from a password system to some form of passwordless MFA, such as a public/private key pair and a single sign-on code.


Web Application 3: Where's the BeEF?

Provide a screenshot confirming that you successfully completed this exploit:




Write two or three sentences outlining mitigation strategies for this vulnerability: 

This is another situation where input validation is one of the best things to do. Adding an escape (\) to every special character (including \, to prevent any double-escape shenanigans), refusing any requests that contain hyperlinks, etc.





© 2023 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.

