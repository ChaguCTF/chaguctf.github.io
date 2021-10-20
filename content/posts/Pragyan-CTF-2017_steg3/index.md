---
title: "Pragyan CTF 2017: Lost Friends (300pts)"
date: 2017-03-05T11:22:32+02:00
draft: false
category: Writeup
tags:
    - Steganography
---
By: [noras] from [ChalmersCTF](http://chalmersctf.se)

##### Challenge Description : 
```
Moana and her friends were out on a sea voyage, spending their summer joyously.
Unfortnately, they came across Charybdis, the sea monster. Charybdis, furious over having
unknown visitors, wreaked havoc on their ship. The ship was lost.

Luckily, Moana survived, and she was swept to a nearby island. But, since then, she has not seen her
friends. Moana has come to you for help. She believes that her friends are still alive, and that you are the
only one who can help her find them.

```
* File : [lost_friends.png](images/lost_friends.png)

#### Solution:

Opening the image with ***stegsolve*** revealed three images in the RGB channels.

![lost_friends.png](images/solved.jpg)

Running strings I found the hint that said 'Director Maybe?'. It was only about googling the director of ```Alvin and the Chipmunks``` and the flag was ```pragyanctf{MikeMitchell}```