### #3 - L0ckB0x ###

This one was the trickiest so far. Since I have very little experience with C and binary reverse engineering, it took a lot of hardwork to get this one done.

First, I did some static analysis in BinaryNinja, before I executed the file in a Kali Linux VM:

chmod +x L0ckB0x

./L0ckB0x

From here, I am presented with a string: "0x4478f6174345fb73540fd87032698d3e." That is interesting, I havent really seen anything like that. I ran the binary again, but this time the last digit of the string changed- "0x4478f6134345fb77540fd87432698d3a." Hm.


This challenge will unlock itself on Mon 30 Sep 2019 3:13:37 PM EDT - wait.. thats not when the challenge released...

What if I set the date and time on my system and executed the binary at that exact second?

`./L0ckB0x >>flag.txt | date >> flag.txt` provides a hexadecimal string that looks similar enough to the other ones, but lets convert it to text with an ASCII table to see.

0x44 - D

0x46 - F

0x43 - C

0x54 - T

0x43 - C

0x7b - {

0x4e - N

0x30 - 0

0x54 - T

0x31 - 1

0x6d - m

0x33 - 3

0x32 - 2

0x57 - W

0x38 - 8

0x7d - }

Mon 30 Sep 2019 03:13:37 PM EDT	>> DFCTC{N0T1m32W8}	

Perfect.




