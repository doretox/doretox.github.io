---
layout: post
title:  "TryHackMe: Nmap Walkthrough"
description: Nmap TryHackMe Room Walkthrough.
date:   2021-03-20 00:00:00 -0500
categories: [TryHackMe]
---

An in depth look at scanning with nmap, a powerful network scanning tool.

# Task 1 - Deploy

No answer needed.

# Task 2 - Introduction

1. What networking constructs are used to direct traffic to the right application on a server?

    **Answer:** ports

2. How many of these are available on any network-enabled computer?

    **Answer:** 65535

3. **[Research]** How many of these are considered "well-known"? (These are the "standard" numbers mentioned in the task)

    **Answer:** 1024

# Task 3 - Nmap Switches

1. What is the first switch listed in the help menu for a 'Syn Scan' (more on this later!)?

    **Answer:** -sS

2. Which switch would you use for a "UDP scan"?

    **Answer:** -sU

3. If you wanted to detect which operating system the target is running on, which switch would you use?

    **Answer:** -O

4. Nmap provides a switch to detect the version of the services running on the target. What is this switch?

    **Answer:** -sV

5. The default output provided by nmap often does not provide enough information for a pentester. How would you increase the verbosity?

    **Answer:** -v

6. Verbosity level one is good, but verbosity level two is better! How would you set the verbosity level to two?

    **Answer:** -vv

7. What switch would you use to save the nmap results in three major formats?

    **Answer:** -oA

8. What switch would you use to save the nmap results in a "normal" format?

    **Answer:** -oN

9. A very useful output format: how would you save results in a "grepable" format?

    **Answer:** -oG

10. Sometimes the results we're getting just aren't enough. If we don't care about how loud we are, we can enable "aggressive" mode. This is a shorthand switch that activates service detection, operating system detection, a traceroute and common script scanning.

    How would you activate this setting?

**Answer:** -A

11. Nmap offers five levels of "timing" template. These are essentially used to increase the speed your scan runs at. Be careful though: higher speeds are noisier, and can incur errors!

    How would you set the timing template to level 5?

    **Answer:** -T5

12. We can also choose which port(s) to scan.

    How would you tell nmap to only scan port 80?

    **Answer:** -p 80

13. How would you tell nmap to scan ports 1000-1500?

    **Answer:** -p 1000-1500

14. A very useful option that should not be ignored:

    How would you tell nmap to scan *all* ports?

    **Answer:** -p-

15. How would you activate a script from the nmap scripting library (lots more on this later!)?

    **Answer:** --script

16. How would you activate all of the scripts in the "vuln" category?

    **Answer:** --script=vuln

# Task 4 - [Scan Types] Overview

No answer needed.

# Task 5 - [Scan Types]

1. hich RFC defines the appropriate behaviour for the TCP protocol?

    **Answer:** RFC 793

2. If a port is closed, which flag should the server send back to indicate this?

    **Answer:** RST

# Task 6 - [Scan Types] SYN Scans

1. There are two other names for a SYN scan, what are they?

    **Answer:** Half-Open, Stealth

2. Can Nmap use a SYN scan without Sudo permissions (Y/N)?

    **Answer:** N

# Task 7 - [Scan Types] UDP Scans

1. If a UDP port doesn't respond to an Nmap scan, what will it be marked as?

    **Answer:** open|filtered

2. When a UDP port is closed, by convention the target should send back a "port unreachable" message. 
    Which protocol would it use to do so?

    **Answer:** ICMP

# Task 8 - [Scan Types] NULL, FIN and Xmas

1. Which of the three shown scan types uses the URG flag?

 **Answer:** xmas

2. Why are NULL, FIN and Xmas scans generally used?

 **Answer:** Firewall Evasion

3. Which common OS may respond to a NULL, FIN or Xmas scan with a RST for every port?

 **Answer:** Microsoft Windows

 # Task 9 - [Scan Types] ICMP Network Scanning

1. How would you perform a ping sweep on the 172.16.x.x network (Netmask: 255.255.0.0) using Nmap? (CIDR notation)

**Answer:** nmap -sn 172.16.0.0/16

# Task 10 - [NSE Scripts] Overview

1. What language are NSE scripts written in?

**Answer:** Lua

2. Which category of scripts would be a very bad idea to run in a production environment?

**Answer:** intrusive

# Task 11 - [NSE Scripts] Working with the NSE

1. What optional argument can the ftp-anon.nse script take?

    **Answer:** maxlist

# Task 12 - [NSE Scripts] Searching for Scripts

1. Search for "smb" scripts in the ````/usr/share/nmap/scripts/` ```directory using either of the demonstrated methods. What is the filename of the script which determines the underlying OS of the SMB server?

    **Answer:** smb-os-discovery.nse

2. Read through this script. What does it depend on?

    **Answer:** smb-brute

# Task 13 - Firewall Evasion

1. Which simple (and frequently relied upon) protocol is often blocked, requiring the use of the ````-Pn```` switch?

    **Answer:** ICMP

2. **[Research]** Which Nmap switch allows you to append an arbitrary length of random data to the end of packets?

    **Answer:** --data-lenght

# Task 14 - Practical

1. Does the target (````MACHINE_IP````) respond to ICMP (ping) requests (Y/N)?

    ![Nmap Ping](/images/nmap-walkthrough/nmap-ping.png)

    **Answer:** N

2. Perform an Xmas scan on the first 999 ports of the target -- how many ports are shown to be open or filtered?

    ![Nmap Xmass](/images/nmap-walkthrough/nmap-xmass.png)

    **Answer:** 999

3. There is a reason given for this -- what is it?

    ![Nmap No Response](/images/nmap-walkthrough/nmap-no-response.png)
    
    **Answer:** no response

4. Perform a TCP SYN scan on the first 5000 ports of the target -- how many ports are shown to be open?

    ![Nmap TCP SYN Scan](/images/nmap-walkthrough/nmap-tcp-syn.png)
    
    **Answer:** 5

5. Deploy the ```ftp-anon``` script against the box. Can Nmap login successfully to the FTP server on port 21? (Y/N)

    ![Nmap ftp-anon script](/images/nmap-walkthrough/nmap-ftp.png)
    
    **Answer:** Y

# Task 15 - Conclusion

No answer needed.