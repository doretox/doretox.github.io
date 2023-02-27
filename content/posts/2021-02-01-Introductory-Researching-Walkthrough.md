---
layout: post
title:  "TryHackMe: Introductory Researching Walkthrough"
description:  Introductory Researching TryHackMe Room Walkthrough - How to solve it.
date:   2021-02-01 00:00:00 -0500
tags: [TryHackMe]
---
This room covers a brief introduction to research skills for pentesting.

To access the room you can click here: <a href="https://tryhackme.com/room/introtoresearch" target="_blank">https://tryhackme.com/room/introtoresearch</a>

# Task 1 - Introduction

No answer needed.

# Task 2 - Example Research Question

1. In the Burp Suite Program that ships with Kali Linux, what mode would you use to manually send a request (often repeating a captured request numerous times)?

    **Answer:** Repeater

2. What hash format are modern Windows login passwords stored in?

    **Answer:** NTLM

3. What are automated tasks called in Linux?

    **Answer:** Cron Jobs

4. What number base could you use as a shorthand for base 2 (binary)?

    **Answer:** Base 16

5. If a password hash starts with $6$, what format is it (Unix variant)?

    **Answer:** sha512crypt

# Task 3 - Vulnerability Searching

1. What is the CVE for the 2020 Cross-Site Scripting (XSS) vulnerability found in WPForms?

    **Answer:** CVE-2020-10385

2. There was a Local Privilege Escalation vulnerability found in the *Debian* version of Apache Tomcat, back in 2016. What's the CVE for this vulnerability?

    **Answer:** CVE-2016-1240

3. What is the very first CVE found in the VLC media player?

    **Answer:** CVE-2007-0017

4. If you wanted to exploit a 2020 buffer overflow in the sudo program, which CVE would you use?

    **Answer:** CVE-2019-18634

# Task 4 - Manual Pages

SCP is a tool used to copy files from one computer to another.

1. What switch would you use to copy an entire directory?

    **Answer:** -r

    fdisk is a command used to view and alter the partitioning scheme used on your hard drive.

2. What switch would you use to list the current partitions?

    **Answer:** -l

    nano is an easy-to-use text editor for Linux. There are arguably better editors (Vim, being the obvious choice); however, nano is a great one to start with.

3. What switch would you use to make a backup when opening a file with nano?

    **Answer:** -B

Netcat is a basic tool used to manually send and receive network requests.

4. What **command** would you use to start netcat in listen mode, using port 12345?

    **Answer:** nc -l -p 12345

# Task 5 - Final Thoughts

No answer needed.