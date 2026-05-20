---
title: "To Infinity and Beyond! Capturing Forever with Tshark"
url: "https://blog.wireshark.org/2014/07/to-infinity-and-beyond-capturing-forever-with-tshark/"
date: "Tue, 08 Jul 2014 00:57:25 +0000"
author: ""
feed_url: "https://blog.wireshark.org/index.xml"
---
Over the last couple of years that I’ve been involved with Wireshark, one issue has reared its head a significant number of times in a surprisingly varied number of ways. These range from “Capturing with tshark uses more and more memory!” to “I set tshark to capture in the background, and it keeps crashing!” to “How do I set up tshark to capture forever?” Historically we’ve had no good answer to these complaints – Wireshark and tshark both only do what is called stateful dissection. This means that they store what they’ve seen in memory and use that information to provide additional details…
