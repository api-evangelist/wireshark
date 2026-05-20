---
title: "Running Wireshark as You"
url: "https://blog.wireshark.org/2010/02/running-wireshark-as-you/"
date: "Thu, 04 Feb 2010 20:11:57 +0000"
author: ""
feed_url: "https://blog.wireshark.org/index.xml"
---
Running Wireshark on Linux involves an interesting challenge 1 : Capturing packets requires root access, but Wireshark is big program and we strongly recommend against running it with elevated privileges. On Linux it’s common to see Wireshark running as root, but this is nearly unheard for similarly-sized applications like Firefox and GIMP. How can we avoid running Wireshark as root?
