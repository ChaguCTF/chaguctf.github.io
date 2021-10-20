---
title: "Pragyan CTF 2017: Answer to Everything (50pts)"
date: 2017-03-05T11:22:32+02:00
draft: false
tags:
    - Reverse Engineering
category: Writeup
---


##### Challenge Description : 
```
Shal has got a binary. It contains the name of a wise man and his flag. He is unable to solve it.

Submit the flag to unlock the secrets of the universe.

NOTE :- Please enclose the flag in the format pragyanctf{<flag>}.

Hint! Sometimes, the best place to hide is plain sight.
Hint! SHAl didn't try one thing, which is what he is.
```
* File : [main.exe](files/main.exe)

#### Solution:

I started by firing up the IDA to analyze the binary after running ```file``` which told me its an ```ELF64``` binary.
After looking fast at the disassembly I could see that it first asks for an input (a number) then call a function ```not_the_flag()```

![main](images/main.png)

The function looked like this:

![fun](images/fun.png)

We tried to submit the flag as ```pragyanctf{kdudpeh}``` but it did not work. Doing some ROT revealed the key "harambe". Looking at the released hints we realized we should use the SHA1 representation of the word. And we got the flag. ```pragyanctf{31a0d851ea10ad886ad4e99ed05892de06998ab9}```
