    Cybersecurity
Module 2 Challenge Submission File



Assessing Security Culture

Make a copy of this document to work in, and then answer each question below the prompt. Save and submit this completed file as your Challenge deliverable.


Step 1: Measure and Set Goals

Using outside research, indicate the potential security risks of allowing employees to access work information on their personal devices. Identify at least three potential attacks that can be carried out.

Lost/Stolen Devices - If a laptop or smartphone is not properly secured, whoever has access to it can access ALL information that isn’t stored behind a password. Company emails, spreadsheets, and other sensitive information is at risk.
Inter-App Data Harvesting - Some applications on a personal device might have tracking features which log images, text, and other data even when the user is not using the app. Even others have looser permissions on executing code that might be placed inside the app by malicious actors. As a result, sensitive information may be logged through the offending application that can later be accessed by prying eyes.
Insecure Networks - Public WiFi (such as at a café or airport) can be tracked and logged by observers or spoofed by man in the middle attacks, meaning any unencrypted information is completely visible to whoever is monitoring the traffic.


Based on the previous scenario, what is the preferred employee behavior? (For example, if employees were downloading suspicious email attachments, the preferred behavior would be that employees only download attachments from trusted sources.)

In an ideal world, the employees would only access work data on approved devices, while connected to approved networks. Any devices used would be protected by a secure PIN (randomly assigned 4/8 digit number) and some form of biometric authentication (facial recognition or fingerprint). Non-work related applications would not be installed on the devices, and non-work interactions like posting on social media would not happen in any proximity to work-related interactions. Finally, the employees would only be connecting to work servers when utilizing an approved encryption schema, such as a private or work-approved VPN.


What methods would you use to measure how often employees are currently not behaving according to the preferred behavior? (For example, conduct a survey to see how often people download email attachments from unknown senders.)

To limit the amount of direct on-device tracking (if possible, respecting the general privacy of the employees is something I would consider preferable for instilling a mutual degree of trust between security and staff), having a log inside the organization’s servers of the IP address and device used to connect to a given user’s account on the servers should provide sufficient data for where and how employees are accessing the confidential information. 

Additionally, security could conduct a cross-reference of when employees post on the business’s Slack channels and when they access their accounts on company servers (like requesting new emails from the company’s mail server) with when the employee is clocked in vs clocked out, to see how often they’re checking work-related information while out of the office.


What is the goal that you would like the organization to reach regarding this behavior? (For example, to have less than 5% of employees downloading suspicious email attachments.)

An incident rate of 0% is ideal, as all employees should avoid risking contamination of security. Assuming that there will always be employees who check personal applications at work and employees who want to check work applications while out of the office or when traveling for business, minimizing the amount of contamination to 2% seems achievable, and with proper security controls (such as VPNs and company-issued devices that limit improper usage) that amount can be safely and reasonably quarantined during usage. 



Step 2: Involve the Right People
 
List at least five employees or departments that should be involved. For each person or department, describe in 2–3 sentences what their role and responsibilities will be.

CIO/CISO & IT Department - The CIO would approve the initial data tracking, and once controls are to be implemented IT would issue and configure the devices and services that employees use. The IT department would also have to provide additional technical support for issues that may arise when employees try to access work related services on new devices.
CFO - As part of the security plan, the CFO would approve any expenditures for purchasing devices/services, or employee expenses if they purchase company-approved services. Security would also likely have to account for time taken during training that is not spent working, or any temporary loss of productivity as employees adapt to not doing work during off-the-clock hours or otherwise limiting their work interactions’ cross-pollination with personal interactions. 
Management - In order to ensure compliance, team leads and other managers should lead by example; they are more likely to be checking work emails/services during time off the clock and employees need to see that leadership is taking these security measures seriously. Additionally, they would assist in the onboarding process for new hires to help them adapt to the security protocols.
COO - Operations needs to remain as smooth as possible during any transitionary period, so regular communication with and feedback from the COO will allow security to roll out updates to protocol on a departmental or otherwise segmented basis. The COO would also be involved to approve of business practice changes and, like the CFO, to account for any loss of productivity to minimize impact on the business’s day-to-day.
Human Resources - HR’s participation would be essential to protect the privacy of employees and to handle any concerns that may arise from employees as training and controls are implemented. HR would also facilitate training schedules, working with the COO to find optimal times and groups to bring into the new protocols while reducing friction for business operations.
CEO - The chief executive would sign off on any final decisions and coordinate with the CFO and COO to keep the business working as it should be. Additionally, the CEO would be the most visible sign of compliance; if even the CEO is avoiding risking the security of the business, the importance of the security protocols would be reinforced throughout the business hierarchy.



Step 3: Training Plan

How frequently will you run training? What format will it take (e.g., in-person, online, a combination of both)?

Training would be rolled out throughout the company on a bi-weekly basis, with follow up training at 1 month, 3 months, and 6 months to iron out inconsistencies and to reinforce good habits. Initial training and the 6 month follow-up would be done in person to supervise the process for employees. The intermediary follow-ups could be done online, as it will both reduce the amount of time taken off of work for training and will allow for in media res analysis of how well training is working - if an employee is doing the training on a personal device and/or through an insecure network, we can flag them for additional training/supervision to ensure compliance.


What topics will you cover in your training, and why? (This should be the bulk of the deliverable.)

The potential risks when using a personal device for work, as well as the potential risks that affect employees even outside of work on their personal devices. The focus would be on the various ways that personal applications like social media and malicious actors intercepting data on public wifi risks not just work information but also personal information, and how those risks can impact the employee and those they care about.
How to secure all of your devices - both work devices and personal devices. Stress the importance of having loss prevention measures like remote device locking/erasing and secure PINs, limiting usage of public WiFi and properly configuring home networks (especially for remote/WFH employees), and identifying and setting up reliable/secure VPNs for both business and private use. 
Temptation-Resistance: strategies that will help employees avoid wanting to check work emails and other work-related applications while at home, discussions on the mental health benefits of “unplugging”, and exercises that demonstrate how compulsive behaviors like constantly checking in on emails/slack servers can actually reduce their productive capacity while making them feel as though they are being productive.
Proper segregation of information: how a “work device” and a “personal device” can be implemented into a daily routine; how to set up additional user accounts on personal devices that will improve focus, reduce stress, and limit security compromises; how to minimize the spread of personal information as well as sensitive company information.


After you’ve run your training, how will you measure its effectiveness? 

Continue to monitor the locations and devices used to connect to company servers, and conduct anonymous surveys with employees on a quarterly basis. 



Bonus: Other Solutions

List at least two other potential solutions. For each one, indicate the following:
What type of control is it? Administrative, technical, or physical? 
What goal does this control have? Is it preventive, deterrent, detective, corrective, or compensating?
What is one advantage of each solution? 
What is one disadvantage of each solution?

Provide employees with dedicated, preconfigured work devices - company phone, company laptop, company VPN. 

This is a technical control with a goal of corrective behavior: if employees have a separate device combined with company policies that encourage segregation between work and personal devices, security can minimize the chance of data leakage. 

One advantage of this solution is that it can be used to control access (ex employees can’t connect to the company servers if the only way to access it remotely is with a company device) and to detect possible insider threats (if the only access point is through the device, it’s easier to trace where a possible threat may come from).

One disadvantage of this is the relatively high cost compared to other solutions - each employee needs a device, and they will likely expect that device to be replaced regularly enough to keep up with new technology. 


Create a new interaction layer for employees that filters their access based on the device and IP location, where out-of-office connections and smartphones are isolated from the rest of the network and information that is accessed is filtered to minimize the sharing of sensitive data.

This is also a technical control, with a goal of preventative behavior: even if security can’t eliminate the risk of employees using personal devices, proper quarantine can mitigate the biggest risks of data exposure.

One advantage for this method is that if employees are resistant to stop using their personal devices, this can provide an alternative solution that would provide a “second-best” outcome. 

One disadvantage for this method is that it’s an additional layer of complexity for IT to handle, and an imperfect solution at that. Having to create and update filters as devices change for a solution that still has certain risks can be a problem that’s more difficult to manage long term.
