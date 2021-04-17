---
layout: post
title:  "TryHackMe: Linux Fundamentals Part 2 Walkthrough"
description:  Linux Fundamentals Part 2 TryHackMe Room Walkthrough - How to solve it.
date:   2021-01-22
 00:00:00 -0500
categories: [TryHackMe]
---
This room is the second part in the Linux Fundamental rooms designed to teach you about various Linux concepts, and in-built tools. This room covers the following topics:
* Linux Operators
* Advanced File Operators

To access the room you can click here: <a href="https://tryhackme.com/room/linux2" target="_blank">https://tryhackme.com/room/linux2</a>

# Task 1 - Intro

No answer needed.

# Task 2 - SSH - Intro

No answer needed.

# Task 3 - Putty and SSH

No answer needed.

# Task 4 - [Section 4: Linux Operators]: "&&"

No answer needed.

# Task 5 - [Section 4: Linux Operators]: "&"

No answer needed.

# Task 6 - [Section 4: Linux Operators]: "$" 

1. How would you set nootnoot equal to 1111?

    **ANSWER:**  export nootnoot=1111

2. What is the value of the home environment variable?

    **ANSWER:** /home/shiba2

# Task 7 - [Section 4: Linux Operators]: "|"

No answer needed.

# Task 8 - [Section 4: Linux Operators] - ";"

No answer needed.

# Task 9 - [Section 4: Linux Operators]: ">"

1. How would you output twenty to a file called test?

    **ANSWER:** echo twenty > test

# Task 10 - [Section 4: Linux Operators]: ">>"

No answer needed.

# Task 11 - Binary - shiba2

1. What is shiba3's password?

    Set the $USER variable to 'test1234' and execute the shiba2 binary.

    ![Shiba2 Password](/images/linux-fundamentals-part2/shiba2.png)

    **ANSWER:** happynootnoises

# Task 12 - [Section 5 - Advanced File Operations]: Intro

No answer needed.

# Task 13 - [Section 5 - Advanced File Operators]: A bit of background.

No answer needed.
 
# Task 14 - [Section 5: Advanced File Operations]: chown

1. How would you change the owner of file to paradox?

    **ANSWER:** chown paradox file

2. What about the owner and the group of file to paradox

    **ANSWER:** chown paradox:paradox file

3. What flag allows you to operate on every file in the directory at once?

    **ANSWER:** -R

# Task 15 - [Section 5: Advanced File Operations]: chmod

1. What permissions mean the user can read the file, the group can read and write to the file, and no one else can read, write or execute the file?

    **ANSWER:** 460

2. What permissions mean the user can read, write, and execute the file, the group can read, write, and execute the file, and everyone else can read, write, and execute the file.

    **ANSWER:** 777

# Task 16 - [Section 5: Advanced File Operations]: rm

1. What flag deletes every file in a directory?

    **ANSWER:** -r

2. How do you suppress all warning prompts?

    **ANSWER:** -f

# Task 17 - [Section 5: Advanced File Operations]: mv

1. How would you move file to /tmp?

    **ANSWER:** mv file /tmp

# Task 18 - Linux Fundamentals 3

No answer needed.