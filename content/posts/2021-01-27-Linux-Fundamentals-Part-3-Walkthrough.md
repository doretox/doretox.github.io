---
layout: post
title:  "TryHackMe: Linux Fundamentals Part 3 Walkthrough"
description:  Linux Fundamentals Part 3 TryHackMe Room Walkthrough - How to solve it.
date:   2021-01-27 00:00:00 -0500
tags: [TryHackMe]
---
This room is the third part in the Linux Fundamental rooms designed to teach you about various Linux concepts, and in-built tools. This room covers the following topics:
* Advanced File Operators (Continued From Linux Fundamentals Part 2)
* Users & Groups
* Introduction To Shell Scripting

To access the room you can click here: <a href="https://tryhackme.com/room/linux3" target="_blank">https://tryhackme.com/room/linux3</a>

# Task 1 - Intro
No answer needed.

# Task 2 - [Section 5: Advanced File Operations] - cp
No answer needed.

# Task 3 - [Section 5: Advanced file Operations] - cd && mkdir

1. Using relative paths, how would you cd to your home directory.

    **ANSWER:** cd ~

2. Using absolute paths how would you make a directory called test in /tmp

    **ANSWER:** mkdir /tmp/test

# Task 4 - [Section 5: Advanced File Operations] ln

1. How would I link /home/test/testfile to /tmp/test?

    **ANSWER:** ln /home/test/testfile /tmp/test

# Task 5 - [Section 5 - Advanced File Operations]: find

1. How do you find files that have specific permissions?

    **ANSWER:** -perm

2. How would you find all the files in /home?

    **ANSWER:** find /home

3. How would you find all the files owned by paradox on the whole system?

    **ANSWER:**: find / -user paradox

# Task 6 - [Section 5: Advanced File Operations] - grep

1. What flag lists line numbers for every string found?

    **ANSWER:** -n

2. How would I search for the string boop in the file aaaa in the directory /tmp?

    **ANSWER:** grep boop /tmp/aaaa

# Task 7 - Binary - Shiba3

1. What is shiba4's password?

    First, the actual binary will check for two things: 1. that there's a directory called test in your home directory and 2. that inside the directory there's a file called test1234. You can create this files if it doesn't exist using 'mkdir' and 'touch' as you learned in the previous rooms.
    The second step is to find the shiba4 binary. To do this we'll use the 'find' and the 'grep' command as you can see in the picture below.

    ![Find Shiba4](/images/linux-fundamentals-part3/shiba3-1.png)

    The result will be:

    ![Find Shiba4 2](/images/linux-fundamentals-part3/shiba3-2.png)

    To find show the password execute the shiba4 binary.

    ![Shiba4 Password](/images/linux-fundamentals-part3/shiba3-3.png)

    **ANSWER:** test1234

# Task 8 - [Section 6: Miscellaneous]: Intro

No answer needed.

# Task 9 - [Section 6: Miscellaneous]: sudo

1. How do you specify which user you want to run a command as.

    **ANSWER:** -u

2. How would I run whoami as user jen?

    **ANSWER:** sudo -u jen whoami

3. How do you list your current sudo privileges(what commands you can run, who you can run them as etc.) 

    **ANSWER:** -l

# Task 10 - [Section 6: Miscellaneous]: Adding users and groups

1. How would I add the user test to the group test?

    **ANSWER:** sudo usermod -a -G test test

# Task 11 - [Section 6: Miscellaneous]: nano

No answer needed.

# Task 12 - [Section 6: Miscellaneous]: Basic shell scripting

No answer needed.

# Task 13 - [Section 6: Miscellaneous]: Important Files and Directories

No answer needed.

# Task 14 - [Section 6 - Miscellaneous]: Installing packages(apt)

No answer needed.

# Task 15 - [Section 6: Miscellaneous]: Processes
No answer needed.