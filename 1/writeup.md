### #1- Suspicious ###

This was the first challenge for Deloitte's 2019 Cyber Threat Competition. After downloading the folder, I opened it up, and saw 15 seemingly identical pdf files (1.pdf - 15.pdf). After opening up the first few and seeing the same message on each - "Almost there, look closer," I got tired and decided to check the file size for each rather than open up all 15 and look at them. 14 of them were 979 bytes, but 8.pdf was 12kb. This was significantly larger, than the rest, so I knew the flag had to be here.

I opended it up, and along with the same text "Almost there, look closer," there was a picture of a knife. Interesting. From here, I went into the terminal. I verified that it was indeed a pdf file 'file 8.pdf'

From here I delved a little deeper. I did 'strings 8.pdf,' and was presented with mostly jibberish, but hidden in between the creator and product, 'Hacker' and 'Evil Guy,' respectively, I noticed '<pdfx:Flag>IRDEGVCDPNUWIZLTN5TG2YLSMNUH2===</pdfx:Flag>'

Could it really be that simple, was that the flag? Almost. At first, I assumed that it was a Base64 encoding, but when I decoded it, I was also presented with jibberish. After a little more research, I discovered that it was in fact Base32 encoding, and was able to decode that and get the flag:

'DFCTC{idesofmarch}'

Now the knife makes sense.