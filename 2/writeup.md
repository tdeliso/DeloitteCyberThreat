### #2- Strange Bulbs ###

For this challenge, we were tasked with analyzing a .pcap file to figure out when and where a keylogger were placed on our clients system. I opened up the file in WireShark.

A keylogger can use any form of communication so transmit data, so I knew I could eliminate any ARP or DNS queries. 

I first analyzed the HTTP packets, and I saw 'Full request URI: http://192.168.0.187:8000/bulbs_indoors.docm,' which I thought was interesting. Bulbs indoors could be related to the hint "Gardening could be quite dangerous" and the title of the challange, *strange bulbs*

I tried a few things after this. I followed that stream, and dug through the ASCII and hex dumps. Nada. From here, I was a little bit lost. I knew I was on the right trail, but I couldn't figure out where to go from here. I tried to make GET and POST requests to that url with the docm via Postman, but still, nothing. Then it hit me, wireshark can be used to export files picked up when sniffing packets.

I exported the bulbs_indoors.docm file by going to File > Export Objects, and I thought that would be that. 

Upon opening it, I was greeted with a short paper about gardening, and an error message that popped up from the autorun macro. I went into the developer tab, and stepped through the VBA code that wouldn't run due to an ActiveX error on my computer. I discovered that all the code did was pull the text from Pastebin and store it in 2 files: \bulb.txt and \indoor.txt. I followed the links to Pastebin, and discovered a PGP private key for 'indoor.txt' and a BASE 64 encoding for 'bulb.txt.' I decoded this, and I had the public key. From here, I did some research on PGP encryption and decryption, and eventually landed on https://www.igolder.com/PGP/decryption/. I pasted the public and private keys, as well as the PGP passphrase 'indoor,' and was greeting with the flag: 'DFCTC{thisisdatflagthocongrats}.'



