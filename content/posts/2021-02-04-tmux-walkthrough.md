---
layout: post
title:  "TryHackMe: tmux Walkthrough"
description:  tmux TryHackMe Room Walkthrough - How to solve it.
date:   2021-02-04 00:00:00 -0500
tags: [TryHackMe]
---
This room covers the basics of one of the most powerful multi-tasking tools on linux.

To access the room you can click here: <a href="https://tryhackme.com/room/rptmux" target="_blank">https://tryhackme.com/room/rptmux</a>

# Task 1 - Screens wishes it was this cool.

1. First things first, let's go ahead and install tmux. This can be done on Ubuntu/Kali with the command: apt-get install tmux

    **No answer needed.**

2. Once tmux is installed, let's launch a new session. What command do we use to launch a new session without a custom name?

    **Answer:** tmux

3. All tmux commands start with a keyboard button combination. What is the first key in this combination?

    **Answer:** Control

4. How about the second key? Note, these keys must be pressed at the same time and released before pressing the next target key in the combination.

    **Answer:** b

5. Lets go ahead and detach from our newly created tmux session. What key do we need to add to the combo in order to detach?

    **Answer:** d

6. Well shoot, we've detached from our session. How do we list all of our sessions?

    **Answer:** tmux ls

7. What did our session name default to when we created one without a set name?

    **Answer:** 0

8. Now that we've found the name of our session, how do we attach to it?

    **Answer:** tmux a -t 0

9. Let's go ahead and make a new window in this session. What key do we add to the combo in order to do this?

    **Answer:** c

10. Seems like we have plenty of windows and nothing to fill them up with. Let's remedy that problem by deploying the VM above and running and nmap scan against it.
     Deploy the VM now.

    **No answer needed.**

11. Run the following scan against the VM: nmap -sV -vv -sC TARGET_IP

    **No answer needed.**

12. Whew! Plenty of output to work with now! If you work with a relatively small terminal like me, this output might not all fit on screen at once. To fix that, let's enter 'copy mode'. What key do we add to the combo to enter copy mode?

    **Answer:** [

13. Copy mode is very similar to 'less' and allows up to scroll up and down using the arrow keys. What if we want to go up to the very top?

    **Answer:** g

14. How about the bottom?

    **Answer:** G

15. What key do we press to exit 'copy mode'?

    **Answer:** q

16. This window we're working in is nice and all but I think we need an upgrade. What key do we add to the combo to split the window vertically?

    **Answer:** %

17. How about horizontally?

    **Answer:** "

18. We can now move between these panes using the key combo and arrow keys, try it out!

    **No answer needed.**

19. We can also resize these panes by holding down the key combo and pressing the arrow keys, try it out now!

    **No answer needed.**

20. Wait a minute, we've forgotten about our original window! We can go back it using the key combo and the number of the session! Try going back to this original window and then returning to our new one!

    **No answer needed.**

21. Say one of these newly minted panes becomes unresponsive or we're just done working in it, what key do we add to the combo to 'kill' the pane?

    **Answer:** x

22. Now that's we've finished out work, what can we type to close the session?

    **Answer:** exit

23. Last but now least, how do we spawn a named tmux session named 'neat'?

    **Answer:** tmux new -s neat