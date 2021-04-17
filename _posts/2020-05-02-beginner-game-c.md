---
layout: post
title:  "A really simple guessing game in C"
description: A basic C game with focus on new programmers.
date:   2020-05-02 00:00:00 +0530
categories: [Programming]
---

Here is the first of three basic C programs that I intend to post here as examples. In my early days I struggled to find real programs to exercise and see how concepts are applied.
In this first program, I applied inicial concepts such as:

- variables;
- functions;
- loops (ifs, while...).

I think the only part of my program that can confuse beginners is how I generated a random number here:

```C
srand(time(0));
	int secretNumber = rand() % 100;
```

First of all, computers cannot generate true random numbers. They do this simply because computers follow a set of rules programmed by humans. To know more about random numbers, I strongly recommend you to visit <a href="https://www.random.org/randomness/" target="_blank">random.org</a>. This website has a lot of useful and interesting information about random numbers.

So what do we do to generate these numbers in small programs like mine? We can add a little trick using the current time. Every time we run our program the date will be different from the first time (even if it is for milliseconds).

<a href="https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/" target="_blank">You can read more about random numbers in C/C++ in this website.</a>

If you’re a more experienced programmer feel completely free to change the code and open a Pull Request to make it easier and more beginner friendly. 

<a href="https://github.com/doretox/guessing-game" target="_blank">Click here to access the source code or go to my github</a>, or clicking on the icon in the footer of this website. 
