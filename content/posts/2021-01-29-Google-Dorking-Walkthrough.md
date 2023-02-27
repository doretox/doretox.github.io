---
layout: post
title:  "TryHackMe: Google Dorking Walkthrough"
description:  Google Dorking TryHackMe Room Walkthrough - How to solve it.
date:   2021-01-29 00:00:00 -0500
tags: [TryHackMe]
---
This room explains how Search Engines work and leveraging them into finding hidden content.

To access the room you can click here: <a href="https://tryhackme.com/room/googledorking" target="_blank">https://tryhackme.com/room/googledorking</a>

# Task 1 - Ye Ol' Search Engine

No answer needed.

# Task 2 - Let's Learn About Crawlers

1. Name the key term of what a "Crawler" is used to do

    **ANSWER:** Index

2. What is the name of the technique that "Search Engines" use to retrieve this information about websites?

    **ANSWER:** Crawling

3. What is an example of the type of contents that could be gathered from a website?

    **ANSWER:** Keywords

# Task 3 - Enter: Search Engine Optimisation

No answer needed.

# Task 4 - Beepboop - Robots.txt

1. Where would "robots.txt" be located on the domain "ablog.com"

    **ANSWER:** ablog.com/robots.txt

2. If a website was to have a sitemap, where would that be located?

    **ANSWER:** /sitemap.xml

3. How would we only allow "Bingbot" to index the website?

    **ANSWER:** User-agent: Bingbot

4. How would we prevent a "Crawler" from indexing the directory "/dont-index-me/"?

    **ANSWER:** Disallow: /dont-index-me/

5. What is the extension of a Unix/Linux system configuration file that we might want to hide from "Crawlers"?

    **ANSWER:** .conf

# Task 5 - Sitemaps

1. What is the typical file structure of a "Sitemap"?

    **ANSWER:** XML

2. What real life example can "Sitemaps" be compared to?

    **ANSWER:**Map

3. Name the keyword for the path taken for content on a website

    **ANSWER:** Route

# Task 6 - What is Google Dorking?

1. What would be the format used to query the site bbc.co.uk about flood defences

    **ANSWER:** site: bbc.co.uk flood defences

2. What term would you use to search by file type?

    **ANSWER:** filetype:

3. What term can we use to look for login pages?

    **ANSWER:** intitle: login




