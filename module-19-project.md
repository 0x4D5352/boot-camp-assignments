    Cybersecurity
Module 19 Challenge Submission File

Let’s Go Splunking!

Make a copy of this document to work in, and then respond to each question below the prompt. Save and submit this completed file as your Challenge deliverable.

Step 1: The Need for Speed

Based on the report you created, what is the approximate date and time of the attack?

February 23, 2023 around 14:30


How long did it take your systems to recover? 

9 hours, with normal operations resuming around 22:30 of the same day.


Provide a screenshot of your report:





Step 2: Are We Vulnerable?

Provide a screenshot of your report:




Provide a screenshot showing that the alert has been created: 





Step 3: Drawing the (Base)line

When did the brute force attack occur?

The attack began between 0800 and 0900 on 2020-02-21 and halted between 1300 and 1400 of the same day.


Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring:

The threshold I have chosen is 30. 

My methodology: 

Calculate the mean (≈28.26), median (13), and mode (12) of the baseline time frame.
Calculate the standard deviation of the dataset (≈35.84)
Count the incidence rate of incorrect login counts between 1 and 10 (6), 11 and 20 (21), 21 and 30 (1), 31 and 40 (2), and over 40 (5).

With this information, it seems clear that 20 or fewer failed login attempts per hour aren’t abnormal, at least within the timeframe of the sample data set. There are only 3 incidences of 21-40 failed login attempts per hour, and it is possible that the two incidences in 31-40 are a result of the brute force attack beginning and ending during mid-hour periods, causing bleedthrough in the binning of the dataset. 

A threshold of 35 is likely safe, and is less likely to cause false positives, but at a slight increase in the chance of false negatives and, if the assumption previously stated holds true, could miss a chance at early response. As such, 30 occurrences will result in the rare false positive but effectively guarantee that large scale brute force attempts will be detected early and dealt with quickly.

As an aside, the majority of hours having between 11 and 20 logins may indicate a possible problem with company password policy. It’s advised to revisit policy and conduct employee surveys to determine the best methods for improving employee login success rate, and additional alerts could be implemented for system administrators for non-malicious yet still anomalous spikes in login attempts.


Provide a screenshot showing that the alert has been created:






© 2022 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
