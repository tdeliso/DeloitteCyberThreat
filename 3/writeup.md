### #3 - L0ckB0x ###

This one was the trickiest so far. Since I have very little experience with C and binary reverse engineering, it took a lot of hardwork to get this one done.

First, I did some static analysis in BinaryNinja, before I executed the file in a Kali Linux VM:

chmod +x L0ckB0x

./L0ckB0x

From here, I am presented with a string: "0x4478f6174345fb73540fd87032698d3e." That is interesting, I havent really seen anything like that. I ran the binary again, but this time the last digit of the string changed- "0x4478f6134345fb77540fd87432698d3a." Hm.


This challenge will unlock itself on Mon 30 Sep 2019 3:13:37 PM EDT - wait.. thats not when the challenge released...

What if I set the date and time


