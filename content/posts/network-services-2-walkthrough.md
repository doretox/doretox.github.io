---
layout: post
title:  "TryHackMe: Network Services 2 Walkthrough"
description: Network Services 2 TryHackMe Room Walkthrough.
date:   2023-07-26 00:00:00 -0500
tags: [TryHackMe]
---
### Task 2 Understanding NFS
What does NFS stand for?  

	Network File System

What process allows an NFS client to interact with a remote directory as though it was a physical device?  

	Mounting

What does NFS use to represent files and directories on the server?  

	file handle

What protocol does NFS use to communicate between the server and client?  

	RPC

What two pieces of user data does the NFS server take as parameters for controlling user permissions? Format: parameter 1 / parameter 2  

	user ID / group ID

Can a Windows NFS server share files with a Linux client? (Y/N)  

	Y

Can a Linux NFS server share files with a MacOS client? (Y/N)

	Y

What is the latest version of NFS? [released in 2016, but is still up to date as of 2020] This will require external research.

	4.2

### Task 3 Enumerating NFS  

Conduct a thorough port scan scan of your choosing, how many ports are open?

	7

Which port contains the service we're looking to enumerate?

	2049

Now, use /usr/sbin/showmount -e [IP] to list the NFS shares, what is the name of the visible share?

	/home

Time to mount the share to our local machine!

First, use "_mkdir /tmp/mount_" to create a directory on your machine to mount the share to. This is in the /tmp directory- so be aware that it will be removed on restart.

Then, use the mount command we broke down earlier to mount the NFS share to your local machine. Change directory to where you mounted the share- what is the name of the folder inside?

	cappucino

Have a look inside this directory, look at the files. Looks like  we're inside a user's home directory...

	(no answer needed)

Interesting! Let's do a bit of research now, have a look through the folders. Which of these folde**rs**
could cont**a**in keys that would give us remote access to the server?

	.ssh

Which of these keys is most useful to us?

	id_rsa 


Copy this file to a different location your local machine, and change the permissions to "600" using "chmod 600 [file]".

Assuming we were right about what type of directory this is, we can pretty easily work out the name of the user this key corresponds to.

Can we log into the machine using _ssh -i \<key-file> \<username>@\<ip>_ ? (Y/N)

	Y

### Task 4 Exploiting NFS
First, change directory to the mount point on your machine, where the NFS share should still be mounted, and then into the user's home directory.  

	 (no answer needed)

Download the bash executable to your Downloads directory. Then use "cp ~/Downloads/bash ." to copy the bash executable to the NFS share. The copied bash shell must be owned by a root user, you can set this using "sudo chown root bash"  

	 (no answer needed)

Now, we're going to add the SUID bit permission to the bash executable we just copied to the share using "sudo chmod +[permission] bash". What letter do we use to set the SUID bit set using chmod?  

	 s

Let's do a sanity check, let's check the permissions of the "bash" executable using "ls -la bash". What does the permission set look like? Make sure that it ends with -sr-x.  
![[Pasted image 20230725093228.png]]

	 -rwsr-sr-x

Now, SSH into the machine as the user. List the directory to make sure the bash executable is there. Now, the moment of truth. Lets run it with "_./bash -p_". The -p persists the permissions, so that it can run as root with SUID- as otherwise bash will sometimes drop the permissions.  

	 (no answer needed)

Great! If all's gone well you should have a shell as root! What's the root flag?

![Task 4 Flag](/images/network-services-2/task4-flag.png)

	THM{nfs_got_pwned}

### Task 5 Understanding SMTP
What does SMTP stand for?  

	Simple Mail Transfer Protocol

What does SMTP handle the sending of? (answer in plural)  

	emails

What is the first step in the SMTP process?  

	SMTP Handshake

What is the default SMTP port?  

	25

Where does the SMTP server send the email if the recipient's server is not available?  

	SMTP queue

On what server does the Email ultimately end up on?  

	POP/IMAP

Can a Linux machine run an SMTP server? (Y/N)  

	Y

Can a Windows machine run an SMTP server? (Y/N)

	Y

### Task 6 Enumerating SMTP

First, lets run a port scan against the target machine, same as last time. What port is SMTP running on?  

	For this one run `nmap -A -p- <machine-ip>`

![Task 6 nmap](/images/network-services-2/task6-nmap.png)

	25

Okay, now we know what port we should be targeting, let's start up Metasploit. What command do we use to do this?

	msfconsole

Let's search for the module "smtp_version", what's it's full module name?  

	auxiliary/scanner/smtp/smtp_version

Great, now- select the module and list the options. How do we do this?  

	options

Have a look through the options, does everything seem correct? What is the option we need to set?  

	RHOSTS

Set that to the correct value for your target machine. Then run the exploit. What's the system mail name?  

	polosmtp.home

What Mail Transfer Agent (MTA) is running the SMTP server? This will require some external research.  

For this one I searched about it on google and find this link: https://www.offsec.com/metasploit-unleashed/scanner-smtp-auxiliary-modules/

	Just rum `smtp_enum` and you'll find the answer.

![SMTP_enum](/images/network-services-2/task6-smtp-enum.png)

	Postfix

Good! We've now got a good amount of information on the target system to move onto the next stage. Let's search for the module "_smtp_enum_", what's it's full module name?

	auxiliary/scanner/smtp/smtp_enum

We're going to be using the _"top-usernames-shortlist.txt"_ wordlist from the Usernames subsection of seclists (/usr/share/wordlists/SecLists/Usernames if you have it installed).

What option do we need to set to the wordlist's path?  

	USER_FILE

Once we've set this option, what is the other essential paramater we need to set?

	RHOSTS

Now, run the exploit, this may take a few minutes, so grab a cup of tea, coffee, water. Keep yourself hydrated!

	(no answer needed)

Okay! Now that's finished, what username is returned?

![Username](/images/network-services-2/task6-username.png)

	Administrator

### Task 7  Exploiting SMTP
  
What is the password of the user we found during our enumeration stage?  

run `**"hydra -t 16 -l administrator -P /usr/share/wordlists/rockyou.txt -vV 10.10.128.200 ssh"**`

![Hydra](/images/network-services-2/task7-hydra.png)

	alejandro

Great! Now, let's SSH into the server as the user, what is contents of smtp.txt

	THM{who_knew_email_servers_were_c00l}

### Task 8 Understanding MySQL

What type of software is MySQL?  

	relational database management system

What language is MySQL based on?  

	SQL

What communication model does MySQL use?  

	client-server

What is a common application of MySQL?  

	back end database

What major social network uses MySQL as their back-end database? This will require further research.

	facebook

### Task 9

As always, let's start out with a port scan, so we know what port the service we're trying to attack is running on. What port is MySQL using?  

for this one I ran `nmap -F -sV <ip>`

![Task 9 nmap](/images/network-services-2/task9-nmap.png)

Good, now- we think we have a set of credentials. Let's double check that by manually connecting to the MySQL server. We can do this using the command "_mysql -h [IP] -u [username] -p_"  

 First you have to enumerate de mysql server. Run `nmap -p 3306 --script=mysql-enum <ip>`
 
![Task 9 mysql-enum](/images/network-services-2/task9-mysql-enum.png)

now run `mysql -h 10.10.5.193 -u root -p` with 'password' as password.

Okay, we know that our login credentials work. Lets quit out of this session with "exit" and launch up Metasploit.  

![MySQL Connect](/images/network-services-2/mysql-connect.png)

 	(no answer needed)

We're going to be using the "mysql_sql" module.

Search for, select and list the options it needs. What three options do we need to set? (in descending order).  
 
![MySQL_sql options](/images/network-services-2/mysql_sql-options.png)

	password/rhosts/username

Run the exploit. By default it will test with the "select version()" command, what result does this give you?  

![MySQL_sql run](/images/network-services-2/mysql_sql-run.png)

	5.7.29-0ubuntu0.18.04.1

Great! We know that our exploit is landing as planned. Let's try to gain some more ambitious information. Change the "sql" option to "show databases". how many databases are returned?

![MySQL Show Databases](/images/network-services-2/mysql_sql-showdatabases.png)

	4

### Task 10 Exploiting MySQL
  
First, let's search for and select the "mysql_schemadump" module. What's the module's full name?  

![MySQL Schemadump](/images/network-services-2/task10-schemadump.png)

	auxiliary/scanner/mysql/mysql_schemadump

Great! Now, you've done this a few times by now so I'll let you take it from here. Set the relevant options, run the exploit. What's the name of the last table that gets dumped?  

	x$waits_global_by_latency

Awesome, you have now dumped the tables, and column names of the whole database. But we can do one better... search for and select the "mysql_hashdump" module. What's the module's full name?

	auxiliary/scanner/mysql/mysql_hashdump


Again, I'll let you take it from here. Set the relevant options, run the exploit. What non-default user stands out to you?  

![MySQL Hashdump](/images/network-services-2/task10-hashdump.png)

	carl

Another user! And we have their password hash. This could be very interesting. Copy the hash string in full, like: bob:*HASH to a text file on your local machine called "hash.txt".

What is the user/hash combination string?  

	carl:*EA031893AA21444B170FC2162A56978B8CEECE18

Now, we need to crack the password! Let's try John the Ripper against it using: "_john hash.txt_" what is the password of the user we found?  

![Task 10 Password](/images/network-services-2/task10-password.png)
	
	doggie

Awesome. Password reuse is not only extremely dangerous, but extremely common. What are the chances that this user has reused their password for a different service?  

What's the contents of MySQL.txt

SSH using 'carl' and 'doggie'

![Task 10 flag](/images/network-services-2/task10-flag.png)

	THM{congratulations_you_got_the_mySQL_flag}