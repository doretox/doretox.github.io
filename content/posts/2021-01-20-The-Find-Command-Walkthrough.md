---
layout: post
title:  "TryHackMe: The find command Walkthrough"
description:  The find command TryHackMe Room Walkthrough - How to solve it.
date:   2021-01-20 00:00:00 -0500
tags: [TryHackMe]
---
Some of the fundamental knowledge that a security professional must have is using properly the Linux ‘find’ command.

At the time I did this room I couldn’t find any blog posts about it to help me with the questions. So, I decided to do this post with all the answers to help anyone who gets stuck. I particularly learn a lot by checking answers and seeing where I’m making mistakes more than getting stuck in a problem and frustanting myself by trying to figure it out by trial and error.

To access the room you can click here: <a href="https://tryhackme.com/room/thefindcommand" target="_blank">https://tryhackme.com/room/thefindcommand</a>
# Task 1 - Start finding

No answer needed.

# Task 2 - Be more specific

1. Find all files whose name ends with ".xml"

    **ANSWER:** find / -type f -name "*.xml"

2. Find all files in the /home directory (recursive) whose name is "user.txt" (case insensitive)

    **ANSWER:** find /home -type f -iname user.txt

3. Find all directories whose name contains the word "exploits"

    **ANSWER:** find / -type d -name "*exploits*"

# Task 3 - Know exactly what you're looking for

1. Find all files owned by the user "kittycat"

    **ANSWER:** find / -type f -user kittycat

2. Find all files that are exactly 150 bytes in size

    **ANSWER:** find / -type f -size 150c

3. Find all files in the /home directory (recursive) with size less than 2 KiB’s and extension ".txt"

    **ANSWER:** find /home -type f -size -2k -name "*.txt"

4. Find all files that are exactly readable and writeable by the owner, and readable by everyone else (use octal format)

    **ANSWER:** find / -type f -perm 644

5. Find all files that are only readable by anyone (use octal format)

    **ANSWER:** find / -type f -perm /444

6. Find all files with write permission for the group "others", regardless of any other permissions, with extension ".sh" (use symbolic format)

    **ANSWER:** find / -type f -perm -o=w -name "*.sh"

7. Find all files in the /usr/bin directory (recursive) that are owned by root and have at least the SUID permission (use symbolic format)

    **ANSWER:** find /usr/bin -type f -user root -perm -u=s

8. Find all files that were not accessed in the last 10 days with extension ".png"

    **ANSWER:** find / -type f -atime +10 -name "*.png"

9. Find all files in the /usr/bin directory (recursive) that have been modified within the last 2 hours

    **ANSWER:** find /usr/bin -type f -mmin -120

# Task 4 - Have you found it?

No answer needed.