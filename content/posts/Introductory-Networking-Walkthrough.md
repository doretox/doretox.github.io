---
layout: post
title:  "TryHackMe: Introductory Networking Walkthrough"
description: Introductory Networking TryHackMe Room Walkthrough - How to solve it.
date:   2021-02-11 00:00:00 -0500
tags: [TryHackMe]
---
An introduction to networking theory and basic networking tools.

To access the room you can click here: <a href="https://tryhackme.com/room/introtonetworking" target="_blank">https://tryhackme.com/room/introtonetworking</a>

# Task 1 - Introduction

No answer needed.

# Task 2 - The OSI Model: An Overview

For the "Which Layer" Questions below, answer using the layer number (1-7)

![OSI Model Layers.](/images/introductory-networking/OSI-layers.png)

1. Which layer would choose to send data over TCP or UDP?

    **Answer:** 4

2. Which layer checks received packets to make sure that they haven't been corrupted?

    **Answer:** 2

3. In which layer would data be formatted in preparation for transmission?

    **Answer:** 2

4. Which layer transmits and receives data?

    **Answer:** 1

5. Which layer encrypts, compresses, or otherwise transforms the initial data to give it a standardised format?

    **Answer:** 5

6. Which layer tracks communications between the host and receiving computers?

    **Answer:** 5

7. Which layer accepts communication requests from applications?

    **Answer:** 6

8. Which layer handles logical addressing?

    **Answer:** 3

9.  When sending data over TCP, what would you call the "bite-sized" pieces of data?

    **Answer:** Segments

10. **[Research]** Which layer would the FTP protocol communicate with?

    **Answer:** 7

11. Which transport layer protocol would be best suited to transmit a live video?

    **Answer:** UDP

# Task 3 - Encapsulation
 
1. How would you refer to data at layer 2 of the encapsulation process (with the OSI model)?

    **Answer:** Frames
 
2. How would you refer to data at layer 4 of the encapsulation process (with the OSI model), if the UDP protocol has been selected?
 
    **Answer:** Datagrams
 
4. What process would a computer perform on a received message?
 
    **Answer:** De-encapsulation
 
5. Which is the only layer of the OSI model to add a trailer during encapsulation?
 
    **Answer:** Data Link
 
6. Does encapsulation provide an extra layer of security (Aye/Nay)?
 
    **Answer:** Aye
 
# Task 4 - The TCP/IP Model
 
1. Which model was introduced first, OSI or TCP/IP?
 
    **Answer:** TCP/IP
 
2. Which layer of the TCP/IP model covers the functionality of the Transport layer of the OSI model (Full Name)?
 
    **Answer:** Transport
 
3. Which layer of the TCP/IP model covers the functionality of the Session layer of the OSI model (Full Name)?
 
    **Answer:** Application
 
4. The Network Interface layer of the TCP/IP model covers the functionality of two layers in the OSI model. These layers are Data Link, and?.. (Full Name)?
 
    **Answer:** Physical
 
5. Which layer of the TCP/IP model handles the functionality of the OSI network layer?
 
    **Answer:** Internet
 
6. What kind of protocol is TCP?
 
    **Answer:** Connection-Based
 
7. What is SYN short for?
 
    **Answer:** Synchronise
 
8. What is the second step of the three way handshake?
 
    **Answer:** SYN/ACK
 
9. What is the short name for the "Acknowledgement" segment in the three-way handshake?
 
    **Answer:** ACK
 
# Task 5 - Wireshark
 
1. What is the protocol specified in the section of the request that's linked to the Application layer of the OSI and TCP/IP Models?
 
    **Answer:** Domain Name System
 
2. Which layer of the OSI model does the section that shows the IP address "172.16.16.77" link to (Name of the layer)?
 
    **Answer:** Network
 
3. In the section of the request that links to the Transport layer of the OSI and TCP/IP models, which protocol is specified?
 
    **Answer:** User Datagram Protocol
 
4. Over what medium has this request been made (linked to the Data Link layer of the OSI model)?
 
    **Answer:** Ethernet II
 
5. Which layer of the OSI model does the section that shows the number of bytes transferred (81) link to?
 
    **Answer:** Physical
 
6. **[Research]** Can you figure out what kind of address is shown in the layer linked to the Data Link layer of the OSI model?
 
    **Answer:** MAC
 
# Task 6 - Networking Tools Ping
 
1. What command would you use to ping the bbc.co.uk website?
 
    **Answer:** ping bbc.co.uk 

1. What is the IPv4 address?
 
    **Answer:** 217.160.0.152
 
3. What switch lets you change the interval of sent ping requests?
 
    **Answer:** -i
 
4. What switch would allow you to restrict requests to IPv4?
 
    **Answer:** -4
 
5. What switch would give you a more verbose output?
 
    **Answer:** -v
 
# Task 7 - Networking Tools Traceroute
 
Use traceroute on tryhackme.com

1. Can you see the path your request has taken?
 
    **No answer needed.**
 
2. What switch would you use to specify an interface when using Traceroute?
 
    **Answer:** -i
 
3. What switch would you use if you wanted to use TCP SYN requests when tracing the route?
 
    **Answer:** -T
 
4. **[Lateral Thinking]** Which layer of the TCP/IP model will traceroute run on by default (Windows)?
 
    **Answer:** Internet
 
# Task 8 - Networking Tools WHOIS
 
1. Perform a whois search on facebook.com
 
    **No answer needed.**
 
2. What is the registrant postal code for facebook.com?
 
    **Answer:** 94025
 
3. When was the facebook.com domain first registered?
 
    **Answer:** 29/03/1997
 
4. Perform a whois search on microsoft.com
 
    **No answer needed.**
 
5. Which city is the registrant based in?
 
    **Answer:** Redmond
 
6. **[OSINT]** What is the name of the golf course that is near the registrant address for microsoft.com?

    If you search on Google ‘golf club near Redmond’ and click on the google maps link you’ll see that the Bellevue Golf Course is the nearest to Redmond.
 
    **Answer:** Bellevue Golf Course
 
7. What is the registered Tech Email for microsoft.com?
 
    **Answer:** msnhst@microsoft.com
 
# Task 9 - Networking Tools Dig
 
1. What is DNS short for?
 
    **Answer:** Domain Name System
 
2. What is the first type of DNS server your computer would query when you search for a domain?
 
    **Answer:** Recursive
 
3. What type of DNS server contains records specific to domain extensions (i.e. .com, .co.uk*, etc)*? Use the long version of the name.
 
    **Answer:** Top-Level Domain
 
4. Where is the very first place your computer would look to find the IP address of a domain?
 
    **Answer:** Local Cache
 
5. **[Research]** Google runs two public DNS servers. One of them can be queried with the IP 8.8.8.8, what is the IP address of the other one?
 
    **Answer:** 8.8.4.4
 
6. If a DNS query has a TTL of 24 hours, what number would the dig query show?
 
    **Answer:** 86400
 
# Task 10 - Further Reading
 
**No answer needed.**