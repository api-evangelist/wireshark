---
title: "T-Mobile: Clever or Insane?"
url: "https://blog.wireshark.org/2010/04/t-mobile-clever-or-insane/"
date: "Sun, 11 Apr 2010 00:36:35 +0000"
author: ""
feed_url: "https://blog.wireshark.org/index.xml"
---
I recently got an Android phone. After downloading the Android SDK I noticed that my cellular provider (T-Mobile) was doing something odd. According to the netcfg command they’re using 25.0.0.0/8 on their GPRS/EDGE network: $ netcfg lo UP 127.0.0.1 255.0.0.0 0x00000049 dummy0 DOWN 0.0.0.0 0.0.0.0 0x00000082 rmnet0 UP 25.130.205.212 255.255.255.252 0x00001043 rmnet1 DOWN 0.0.0.0 0.0.0.0 0x00001002 rmnet2 DOWN 0.0.0.0 0.0.0.0 0x00001002 sit0 DOWN 0.0.0.0 0.0.0.0 0x00000080 ip6tnl0 DOWN 0.0.0.0 0.0.0.0 0x00000080 T-Mobile doesn’t own that netblock.
