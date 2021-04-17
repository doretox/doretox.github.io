---
layout: post
title:  "TryHackMe: OhSINT Walkthrough"
description: OhSINT TryHackMe Room Walkthrough - How to solve it.
date:   2020-05-19 00:00:00 -0500
categories: [TryHackMe]
---
OhSINT room is free and can be accessed through the following link: <a href="https://tryhackme.com/room/ohsint" target="_blank">OhSINT.</a> 

The room description is “Are you able to use open source intelligence to solve this challenge?”
Basically, the whole concept of this room is using free tools to find information only based in the picture provided by the room’s author. 

# Step 1 - Download the picture.
![Download the Picture](/images/ohsint-walkthrough/download-file.png)

Now we’ve got a familiar picture - a WindowsXP standard wallpaper.

# Step 2 - Getting information using the downloaded picture.
We can easily get a file metadata using a tool called ExifTool. For more info about this tool you can access <a href="https://exiftool.org/" target="_blank">ExifTool.org</a> and <a href="https://en.wikipedia.org/wiki/ExifTool" target="_blank">Wikipedia - ExifTool.</a>

Navigate to the directory where you saved the picture downloaded in Step 1 and run:<br>

```shell
exiftool WindowsXP.jpg 
```

Your terminal will show something like this:
![ExifTool Terminal](/images/ohsint-walkthrough/exiftool-terminal.png)

How you can see in your terminal output that you have a COPYRIGHT name. So, now it is time to do some Google Dorking.

# Step 3 - Google Dorking.
Whenever you put the nickname that you’ve found on the picture’s metadata on Google, you can already find some cool information.
![Google Search Results](/images/ohsint-walkthrough/google-search.png)

Open and check these 3 links.
All the flags will be found using these 3 search results, so let’s do it in order. 

1. What is this user's avatar of?
    You can find this flag by checking the Twitter account (the first link that appeared on Google search). 

    ![User's avatar](/images/ohsint-walkthrough/profile-pic.png)


    **ANSWER:** cat

2. What city is this person in?
    If you click on the “HINT” button you’ll find this message: BSSID + Wigle.net. From reading all the tweets from the account we found, you can see that his first tweet was:
    ![BSSID Tweet](/images/ohsint-walkthrough/bssid-tweet.png)

    Now you can access <a href="wigle.net" target="_blank">Wigle.net</a>  and go to VIEW -> Basic search and enter the BSSID you found in that tweet. If you zoom out in the map you’ll be able to see a purple point on London.
    ![Location](/images/ohsint-walkthrough/london.png)


    **ANSWER:** London

3. Whats the SSID of the WAP he connected to?
    On Wigle, if you zoom in all the way to the max (very important), at that point on London, you’ll be able to see the SSID of the WAP he connected to.
    ![SSID](/images/ohsint-walkthrough/ssid.png)


    **ANSWER:** unileverwifi

4. What is his personal email address?
    Back to those 3 links we found on Google you’ll be able to find his personal email on the Github that we found in our search.
    ![Email](/images/ohsint-walkthrough/email.png)


    **ANSWER:** OWoodflint@gmail.com

5. What site did you find his email address on?
    This question was responded by finding the flag above.

    **ANSWER:** Github

6. Where has he gone on holiday?
    This flag also is located in one of those three links we found on Google. If you read his only blog post you’ll find where he’s spending his holiday.
    ![Blog Post](/images/ohsint-walkthrough/holiday.png)


    **ANSWER:** New York

7. What is this person's password?
    This flag was the hardest in this room. To find this flag you’ll have to inspect the blog source code. There’s no right way to do this, you’ll have to search the source code for strange patterns or something that doesn’t belong there.
    In this particular case we found a strange “word” that doesn’t fit with the rest of the code, which occurs with this flag. 
    ![Password](/images/ohsint-walkthrough/last-flag.png)


    **ANSWER:** pennYDr0pper.!




