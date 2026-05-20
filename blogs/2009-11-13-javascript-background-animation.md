---
title: "Javascript Background Animation"
url: "https://blog.wireshark.org/2009/11/js-bg-animation/"
date: "Fri, 13 Nov 2009 05:11:26 +0000"
author: ""
feed_url: "https://blog.wireshark.org/index.xml"
---
The Windows 7 taskbar does this nifty little background animation when you mouse over an open application’s icon. I wanted to see if the effect could be duplicated on a web page. Suppose we have a couple of inline elements: <div> <img class="bgmove" src="wsbadge-empty.png"> </div> <h1> <span class="bgmove">Packets!</span> </h1> The image is mostly transparent: We have a background that’s slightly larger than our elements, which lets us position it using negative offsets: .bgmove { background-image: url('wsbadge-bg.png'); background-repeat: no-repeat; background-position: -50px -20px; }…
