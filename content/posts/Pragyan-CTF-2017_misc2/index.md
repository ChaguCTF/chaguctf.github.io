---
title: "Pragyan CTF 2017: The Vault (75pts)"
date: 2017-03-05T11:22:32+02:00
draft: false
tags:
    - Forensics
category: Writeup
---
By: [ChalmersCTF](http://chalmersctf.se)

##### Challenge Description : 
```
[!@# a-z $%^ A-Z &* 0-9] [1,3]
```
File : [file](files/file.kdb)

#### Solution:

Running ```file ``` on the included file revealed that its a keepass file. And the regex seems to be the clue about the password.

```sh
$ file file
file.kdb: Keepass password database 1.x KDB, 3 groups, 4 entries, 50000 key transformation rounds

```

So we generate [passwordlist](files/combos.txt) using the regex

```python
#!/usr/bin/env python
import string
import itertools

table = string.ascii_letters + string.digits + "!@# $%^&*"

with open("combos.txt","w+") as file:
    for x in itertools.combinations(table, 3):
        file.write("".join(x)+"\n")
```

Extract the key from the file and run john to bruteforce it.

```sh
$ mv file file.kdb
$ keepass2john file.kdb > keypasskey
$ john --wordlist=combos.txt  --format=keepass keypasskey
    Session completed
$ john  keypasskey --show
file.kdb:k18

1 password hash cracked, 0 left

```

That revealed the password ```k18```

Opening the file using [http://keepass.info/download.html](http://keepass.info/download.html) we could see the flag.

![flag](files/cap.png)
