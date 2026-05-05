---
title: "Wireshark Is Now Twenty"
url: "https://blog.wireshark.org/2018/07/wireshark-is-now-twenty/"
date: "Sat, 14 Jul 2018 20:31:21 +0000"
author: ""
feed_url: "https://blog.wireshark.org/index.xml"
---
<p>Twenty years ago today I announced Ethereal 0.2.0, which marks the first public release of what is now Wireshark. The release was an attempt at two things: to create an interactive protocol analyzer for Linux and Solaris so that I could do my job better, and to give back to the open source community. As it turns out the second goal had a huge effect on the first one. After the initial release developer and user communities quickly formed. Different people had different goals such as support for other platforms and protocols, troubleshooting in specific environments, education, product development, network forensics, and so on. After a while things settled down to a single goal:</p>
<p><em>To help as many people as possible understand their networks as much as possible.</em></p>
<p>As goals go that’s pretty broad and implies a lot of work. Open source project hosting services didn’t exist in 1998 so in the olden days <a href="https://www.youtube.com/watch?v=Wgn9fAymS2g">we pretty much ate sand</a>. For example, I made thirty releases in the first year. Twenty of them were first two months. That’s because <em>I was our revision control system</em><sup>1</sup>. Contributors would send me patches, I’d apply them to my source tree and then make a release. Everyone would then sync their source directories with the new release. Fortunately we stopped doing that in short order. Other parts of the project followed similar paths. The first Windows packages were ZIP files with no capture driver. Our first web server was a 40 MHz SPARCstation IPX with 64 MB of RAM. We inflicted X11 on our macOS users far longer than we should have.</p>
<p>The project grew from those humble beginnings to what is today â€“ the world’s most popular network protocol analyzer. The goal is still there, and many people and organizations are helping us achieve it. <a href="https://www.riverbed.com/products/steelcentral/index.html">We have a wonderful sponsor in Riverbed</a>, which pays my salary, provides our infrastructure, and sponsors SharkFest, our developer and user conference<sup>2</sup>. It’s managed by Janice Spampinato, who does a spectacular job of making sure our community can share its knowledge face to face in a welcoming environment.Â Speaking of SharkFest, <a href="https://sharkfestus.wireshark.org/">we’re having three of them this year</a>! Laura Chappell does a correspondingly spectacular job with <a href="https://www.wiresharktraining.com/">Wireshark University</a>, educating users throughout the year. Our user and developer community is second to none in its expertise, knowledge, and willingness to help.</p>
<p>I could not be more proud of what we’ve accomplished and look forward to the challenges and opportunities. On behalf of the Wireshark development team, thank you for your support.</p>
<hr />
<ol>
<li>
<p>Never, ever do this. If you want to start a project, just commit your code to GitLab. Or GitHub. Or BitBucket. Or anything else that doesn’t involve manual patching.</p>
</li>
<li>
<p>If your career involves looking at packets you should maybe show up once in a while.</p>
</li>
</ol>
