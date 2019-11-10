### #5 - Hero ###

This challenge was particulary difficult, and took a considerable amount of time, but I was very happy to have solved it.

When analyzing the first picture, I was playing around with color correction in GIMP, and was able to spot the password for the first protected folder

*The Password is SAITAMAISTHEOPM*

No Problem, that only took a few minutes, so lets keep it going.

In the next folder, we had another protected zip file, and an image called "hint.jpg." Seem straight forward enough, we can analyze the image to find the password. This is where I really hit a wall for a few days. I tried everything I could think of in steganalysis - color correction, LSB analysis, numberous steganalysis tools - but nothing. At this point, I had given up trying to find the password in that image, and wondered if I could brute force the password for the zip file with `johhny` or `fcrackzip`. Turns out I was- it found the password "Ok" in about a second, and I was able to unlock the final folder. In here, I found a .apk file, and another .jpg file.

From here, I downloaded an Android Emulator `Bluestacks` and was able to open the Application on my laptop. I was nervous I would have to use an Android specfic exploit, but I was simply presented with a password. From here, I assumed that this was the password to the final .jpg, and I used an online tool to extract any password protected data, and sure enough I was presented with the flag.

DFCTC{ON3_PUNCH_MAN_H3R@}
