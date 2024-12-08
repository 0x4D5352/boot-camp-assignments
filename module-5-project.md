    Cybersecurity
Module 5 Challenge Submission File


Archiving and Logging Data

Make a copy of this document to work in, and then for each step, add the solution command below the prompt. Save and submit this completed file as your Challenge deliverable.


Step 1: Create, Extract, Compress, and Manage tar Backup Archives

Command to extract the TarDocs.tar archive to the current directory:

tar xf (or xvf if you want verbose output) TarDocs.tar
To explicitly state current directory:

tar xf TarDocs.tar .


Command to create the Javaless_Doc.tar archive from the TarDocs/ directory, while excluding the TarDocs/Documents/Java directory:

tar cvf Javaless_Doc.tar -–exclude=’Java’ TarDocs/


Command to ensure Java/ is not in the new Javaless_Docs.tar archive: (note: why does it say Javaless_Docs here when Q2 had us create Javaless_Doc)

tar tvf Javaless_Doc.tar | grep Java


Bonus
 
Command to create an incremental archive called logs_backup_tar.gz with only changed files to snapshot.file for the /var/log directory:

sudo tar cvzf logs_backup.tar.gz -–listed-incremental=snapshot.file /var/log

OR if first backup

sudo tar cvzf logs_backup.tar.gz -–listed-incremental=snapshot.file --level=0 /var/log


NOTE: I’m a little confused by this bonus question. Is “snapshot.file” the literal name of the snapshot archive? If so, why is it not a .snar extension? If it’s supposed to be a more generic name, like a fancy way of writing “...only changed files to the snapshot file”, I’d probably put something like “logs_backup.snar”.
Critical Analysis Question

Why wouldn't you use the options -x and -c at the same time with tar?

-x is for extracting an archive, while -c is for creating an archive. These are fundamentally exclusive actions; you can’t extract an archive that hasn’t been created!

Step 2: Create, Manage, and Automate Cron Jobs

Cron job for backing up the /var/log/auth.log file:

0 6 * * 3 tar czf /auth_backup.tgz /var/log/auth.log

If you want to log the results:

0 6 * * 3 tar cvvzf /auth_backup.tgz /var/log/auth.log >> /auth_backup_logs.txt



Step 3: Write Basic Bash Scripts

Brace expansion command to create the four subdirectories:

Mkdir -p ~/backups/{freemem,diskuse,openlist,freedisk}


Paste your system.sh script edits:

#!/bin/bash
echo “Free memory as of $(date):” >> ~/backups/freemem/free_mem.txt
free -ht >> ~/backups/freemem/free_mem.txt
echo “Disk usage as of $(date):” >> ~/backups/diskuse/disk_usage.txt
du -ht >> ~/backups/freemem/diskuse/disk_usage.txt
echo “All open files as of $(date):” >> ~/backups/openlist/open_list.txt
lsof >> ~/backups/openlist/open_list.txt
echo “Disk usage statistics as of $(date):” >> ~/backups/freedisk/free_disk.txt
df -h --total >> ~/backups/freedisk/free_disk.txt




Command to make the system.sh script executable:

chmod +x system.sh

Optional

Commands to test the script and confirm its execution:

sudo ./system.sh
OR
sudo bash system.sh
THEN
ls -R ~/backups
cat ~/backups/freemem/free_mem.txt
cat ~/backups/diskuse/disk_usage.txt
cat ~/backups/openlist/open_list.txt
cat ~/backups/freedisk/free_disk.txt


Bonus

Command to copy system to system-wide cron directory:

sudo cp ~/system.sh /etc/cron.weekly

(this question seems different from the information in the bonus on the canvas page, taken literally this would be the same command but /etc/cron.d instead of cron.weekly)



Step 4. Manage Log File Sizes
 
Run sudo nano /etc/logrotate.conf to edit the logrotate configuration file. 

Configure a log rotation scheme that backs up authentication messages to the /var/log/auth.log. 

Add your config file edits:

/var/log/auth.log {
    weekly
    rotate 7
    notifempty
    compress
    delaycompress
    missingok 
}





Bonus: Check for Policy and File Violations

Command to verify `auditd` is active:

Systemctl status auditd.service


Command to set number of retained logs and maximum log file size:

sudo vim /etc/audit/auditd.conf (NOTE: i prefer vim over nano)


Add the edits made to the configuration file:

num_logs = 7
max_log_file = 35


Command using auditd to set rules for /etc/shadow, /etc/passwd, and /var/log/auth.log:

sudo vim /etc/audit/rules.d/audit.rules

 
Add the edits made to the rules file below:

-w /etc/shadow -p wra -k hashpass_audit
-w /etc/passwd -p wra -k userpass_audit
-w /var/log/auth.log -p wra -k authlog_audit


Command to restart auditd:

sudo systemctl restart auditd.service


Command to list all auditd rules:

sudo auditctl -l


Command to produce an audit report:

sudo aureport -au


Create a user with sudo useradd attacker and produce an audit report that lists account modifications:

sudo aureport -m


Command to use auditd to watch /var/log/cron:

sudo auditctl -w /var/log/cron


Command to verify auditd rules:

sudo auditctl -l


Bonus (Research Activity): Perform Various Log Filtering Techniques

Command to return journalctl messages with priorities from emergency to error: (NOTE: some commands here work without sudo, but are included for consistency’s sake)

sudo journalctl -p 0..3 (could also use -p emerg..err)


Command to check the disk usage of the system journal unit since the most recent boot:

sudo journalctl -u systemd-journald.service

Can also use “ | less” after this command


Command to remove all archived journal files except the most recent two:

sudo journalctl --vacuum-files=2


Command to filter all log messages with priority levels between zero and two, and save output to /home/sysadmin/Priority_High.txt:

sudo journalctl -p 0..2 >> /home/sysadmin/Priority_High.txt (could also use -p emerg..crit)


Command to automate the last command in a daily cron job. Add the edits made to the crontab file below:

0 0 * * * journalctl -p 0..2 >> /home/sysadmin/Priority_High.txt