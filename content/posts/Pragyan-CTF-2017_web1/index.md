---
title: "Pragyan CTF 2017: Give The Guy (100pts)"
date: 2017-03-05T11:22:32+02:00
draft: false
category: Writeup
tags:
    - Web
    - Bullshit
---
By: [ChalmersCTF](http://chalmersctf.se)

##### Challenge Description : 
```
Hacker G has a website. Can you use it to decipher this cipher text ?

Cipher text :- dobrjtuojxagbqhd

Link : http://139.59.62.216/give_the_guy/

NOTE :- Please enclose the flag in the format pragyanctf{<flag>}.

```

#### Solution:

After brute forcing the challenge, probing for hidden directories/files, it turned out that if you simply run **Affine-cipher** on the ciphertext, you get the flag...

![flag](images/cap.png)