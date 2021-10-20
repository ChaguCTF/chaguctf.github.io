---
title: "Pragyan CTF 2017: Evil Corp (100pts)"
date: 2017-03-05T11:22:32+02:00
draft: false
tags:
    - Cryptography
category: Writeup
---
By: [ChalmersCTF](http://chalmersctf.se)

##### Challenge Description : 
```
fsociety has launched another attack at Evil Corp. However, Evil Corp has decided to encrypt the .dat file with a CBC cipher. Reports reveal that it is not AES and the key is relatively simple, but the IV might be long. And remember, fsociety and evilcorp are closely linked.

NOTE :- Please enclose the flag in the format pragyanctf{<flag>}.

Hint! Snakes serve the fsociety. Hmmm.
Hint! fscociety and evilcorp are too close, even 16 characters long together. Damn

```
File : [fsociety.dat](files/fsociety_new.dat)
#### Solution:

One of the team mates Told me that he is sure that this is Serpent CBC cihper. 

Using this tool: 
[http://serpent.online-domain-tools.com/](http://serpent.online-domain-tools.com/) with the password ```fsociety```. We got [a file](files/odt-IV-c511874ee92bf191b2234edc1cb1cfe0.dat) that looks like an image but missing the **JPG Magic numbers**. Adding the magic numbers using **hexeditor** we could see the image.

![image](files/evil.jpg)

Note: image might not open or show in github :P

flag is ```pragyanctf{HelloFriend}```