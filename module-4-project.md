    Cybersecurity
Module 4 Challenge Submission File

Linux Systems Administration

Make a copy of this document to work in, and then for each step, add the solution commands below the prompt. Save and submit this completed file as your Challenge deliverable.

Step 1: Ensure/Double Check Permissions on Sensitive Files

Permissions on /etc/shadow should allow only root read and write access.

Command to inspect permissions:

ls -l /etc/shadow



Command to set permissions (if needed):

sudo chmod 640 /etc/shadow


Permissions on /etc/gshadow should allow only root read and write access.

Command to inspect permissions:

ls -l /etc/gshadow


Command to set permissions (if needed):

sudo chmod 640 /etc/gshadow


Permissions on /etc/group should allow root read and write access, and allow everyone else read access only.

Command to inspect permissions:

ls -l /etc/group


Command to set permissions (if needed):

sudo chmod 644 /etc/group


Permissions on /etc/passwd should allow root read and write access, and allow everyone else read access only.

Command to inspect permissions:

ls -l /etc/passwd


Command to set permissions (if needed):

sudo chmod 644 /etc/passwd


Step 2: Create User Accounts

Add user accounts for sam, joe, amy, sara, and admin with the useradd command.

Command to add each user account (include all five users):

sudo useradd -m sam
sudo useradd -m joe
sudo useradd -m amy
sudo useradd -m sara
sudo useradd -m admin


Ensure that only the admin has general sudo access.

Command to add admin to the sudo group:

sudo usermod -a -G sudo admin


Step 3: Create User Group and Collaborative Folder

Add an engineers group to the system.

Command to add group:

sudo groupadd engineers


Add users sam, joe, amy, and sara to the managed group.

Command to add users to engineers group (include all four users):

sudo usermod -a -G engineers sam
sudo usermod -a -G engineers joe
sudo usermod -a -G engineers amy
sudo usermod -a -G engineers sara


Create a shared folder for this group at /home/engineers.

Command to create the shared folder:

sudo mkdir /home/engineers


Change ownership on the new engineers’ shared folder to the engineers group.

Command to change ownership of engineers’ shared folder to engineers group:

sudo chgrp -R engineers /home/engineers


Step 4: Lynis Auditing

Command to install Lynis:

sudo apt install lynis


Command to view documentation and instructions:

man lynis


Command to run an audit:

sudo lynis audit system


Provide a report from the Lynis output with recommendations for hardening the system.

Screenshot of report output:



Bonus

Command to install chkrootkit:

sudo apt install chkrootkit


Command to view documentation and instructions:

man chkrootkit


Command to run expert mode:

sudo chkrootkit -x


Provide a report from the chkrootkit output with recommendations for hardening the system.

Screenshot of end of sample output:
