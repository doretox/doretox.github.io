---
layout: post
title:  "The Hacking Methodology"
description: The Hacking Methodology.
date:   2021-10-05 00:00:00 -0500
categories: [Hacking]
---
The hacking methodology is a methodical and logical process that every hacker follows to accomplish a penetration test. This ensures consistency and a pattern to be followed by the industry.

The Process that pentesters follow is:
1. Reconnaissance
2. Enumeration/Scanning
3. Exploitation
4. Privilege Escalation
5. Covering Tracks
6. Reporting

# Reconnaissance
Reconnaissance is the most important step of the process, it is a pretty simple concept. In this phase, the hacker must collect the maximum amount of useful information about the target. Information that will be useful in the next steps of hacking.

To collect this information, the hacker most of the time uses simple and very common tools as:
- Google
- Wikipedia
- Social media (Twitter, LinkedIn, etc)

And others not known for the public in general as:
- PeopleFinder.com
- who.is
- sublist3r
- hunter.io
This phase is called the most important of all hacking methodology because it is based on the information collected here that all next steps will be done.

# Enumeration/Scanning

This is a step where a hacker will interact with the target to attempt to find vulnerabilities, based on the information collected in the Reconnaissance phase.
Tools like Nmap, Metasploit, exploit-dB, Burp Suite, and others are pretty useful to find vulnerabilities.
Nmap ("Network Mapper") is the most used and well-known it can be used to find live hosts on a network, perform port scanning, ping sweeps, OS detection, and version detection. All this information is critical and can lead to a successful pentest.

# Exploitation

Exploitation is the process of planning and executing the attack based on the information obtained in the previous phases (Reconnaissance and Enumeration). In this phase, the attacker performs the actual hacking process using hacking tools, like Metasploit and burp suite.
Metasploit is a framework with built-in scripts that helps to exploit a machine.
Burp Suite is used to exploit web applications.

# Privilege Escalation

After the hacker gains access to the machine, the next step is to escalate privileges from a low-level account (such as a guest account) up to the administrator.

- In Windows systems, the target account is usually: Administrator or System.
- In Linux systems, the target account is usually: root

To escalate privileges the hacker can use:
- Find a vulnerable service;
- Crack a password;
- Use default credentials;
- and others.

# Covering Tracks

Most of the time (at least if not specified in the contract) the ethical hacker/pentester will not need to cover his tracks. But this is still a phase of hacking.
To cover the tracks the hacker will remove any evidence of the attack preset in a system. The attacker erases log files and removes other evidence that the owner of the system can determine that an attack occurred.

# Reporting

In this phase, the ethical hacker writes everything that was found and executed, step by step in high detail.
The report is the final product of penetration testing, where the hacker will show the vulnerabilities, the criticality, how it was exploited, and commonly how to fix it.
You can read a full format report sample here:  ****[https://github.com/hmaverickadams/TCM-Security-Sample-Pentest-Report](https://github.com/hmaverickadams/TCM-Security-Sample-Pentest-Report)


*If you find any errors in this post please don't hesitate to contact me on Twitter at* [@doretox](https://twitter.com/doretox)*. I would be grateful for your help.*