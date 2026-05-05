---
title: "Wireshark Is 25: The email that started it all and the lessons learned along the way"
url: "https://blog.wireshark.org/2023/07/wireshark-is-25/"
date: "Fri, 14 Jul 2023 16:14:30 +0000"
author: ""
feed_url: "https://blog.wireshark.org/index.xml"
---
<p>25 years ago, I <a href="https://mail.gnome.org/archives/gtk-list/1998-July/msg00568.html">sent this email</a>, which ended up changing the course of my life </p>
<pre class="wp-block-preformatted">From: Gerald Combs - Unicom Communications &lt;gerald [at] … &gt;
To: gtk-list [at] redhat . com
Subject: ANNOUNCE: Ethereal 0.2.0
Date: Tue, 14 Jul 1998 21:47:01 -0500 (CDT)

Ethereal is a network analyzer that lets you capture and interactively
browse the contents of Ethernet frames.  Packet data can be read from a
file, or live from a local network interface.

More information, including the source distribution, can be found at
http://ethereal.zing.org . 

Comments and patches are welcome.</pre>
<p>I remember being nervous and excited at the time, wondering what the reaction would be. I had spent the previous few months working on a protocol analyzer, which was something I needed at work.</p>
<p>There are a couple of things to note: the name wasn’t Wireshark (we changed the name in 2006) and at the time of this email, protocol analyzers were rare, you could even say a precious thing. Back then, if you wanted to see what was happening on your network, command line tools like tcpdump and snoop were available at no cost, but if you wanted a GUI analyzer, you had to pay for a product that might cost the equivalent of a luxury car. I needed an analyzer to do my job, so I ended up writing a simple one and releasing it as open source.</p>
<p>As it turned out, other people needed an analyzer too. A couple of days after I sent this email, I received a patch. Then another, and another. This quickly blossomed into a thriving developer community which has kept me busy ever since. In the intervening years, the project and its community have grown beyond any expectation that I could have had. Today, Wireshark is used by people around the world to make their networks fast, reliable, and secure, and educators use it to teach the next generation of security and network engineers about the low-level aspects of networks.</p>
<p>What does it take to keep a project successful for so long? It would be nice to be able to say that from the very beginning, there was a grand, clear vision of how everything would evolve and unfold. However, as with any significant endeavor, you have to learn to adapt and apply the resources at hand as effectively as you can. In retrospect, Neils Bohr’s quote</p>
<p>“An expert is a person who has made all the mistakes that can be made in a very narrow field.”</p>
<p>rings especially true in our case. I did manage to learn that in order for an open source project to grow and thrive, you have to ensure that needs are met in the following categories:</p>
<p><strong>User support</strong>. Living, breathing people make use of your project, and sometimes need assistance. They might be daily power users or novices, and their needs vary.</p>
<p><strong>Educator support</strong>. Experts and power users can teach others how to get the most out of your project, and need assistance as well.</p>
<p><strong>Developer support</strong>. The easier you can make it for people to contribute code or otherwise improve the project, the healthier the project and community will be.</p>
<p><strong>Attorneys and accountants</strong>. Until GitHub and GitLab add “intellectual property law” or “travel reimbursement” buttons, you’re going to need to find outside help for the regulatory, legal, and financial aspects of your project.</p>
<p><strong>Infrastructure</strong>. You need servers, containers, and services that provide an online presence and allow for collaboration. GitHub or GitLab may or may not be sufficient for this depending on your specific needs.</p>
<p>This isn’t quite a <a href="https://en.wikipedia.org/wiki/Maslow%27s_hierarchy_of_needs">Maslow-style hierarchy of needs</a> for open source, but it’s close. The lines between users, educators, and developers can be blurry, but in general, users and educators depend on the output that developers produce, and the project as a whole needs a solid infrastructure in order for everyone to collaborate.</p>
<p>It also doesn’t apply uniformly to all projects. For example, a small, single-purpose image processing library might only need infrastructure and developers, and its user community would likely be other developers. A hosting service like GitHub or GitLab would be sufficient for the project’s infrastructure. On the other hand, a large, feature-rich image editing application might have extensive needs in all five categories along with a business model to fund the project.</p>
<p>Wireshark falls into the latter group, and needs quite a bit of care and feeding. Until recently, the business model for meeting these needs has been “ask my employer if they’ll host the project,” which worked surprisingly well. My employers (CACE Technology, Riverbed and now Sysdig) provided the resources for Wireshark that go way beyond what GitHub and GitLab can offer, such as SharkFest, a <a href="https://sharkfest.wireshark.org">conference dedicated to protocol analysis</a>.</p>
<p>In recent years, it became clear that the project would best meet its needs by standing on its own, and with the help of <a href="https://sysdig.com">Sysdig</a>, we moved the project to the <a href="https://wiresharkfoundation.org">Wireshark Foundation</a> earlier this year so that the project can continue to grow and serve its community.</p>
<p>25 years ago when I sent that email, I never thought I would be blogging about the project today! If you’ve ever thought about starting an open source project, don’t hesitate to do so. Supporting and managing Wireshark has given me a wonderful career, and opportunities to meet and work with brilliant, inspiring people. If I had to distill everything I’ve learned down to a couple of pieces of advice, it would be this:</p>
<p><em>The community has valuable insights to share. Let them do that.</em></p>
<p>Don’t be afraid to start something new. You never know where it might take you 25 years from now.</p>
<p>Finally, I can’t thank you all enough for using and contributing to Wireshark over the years. I can’t wait to see what the future brings. Cheers!</p>
<h2 id="comments">Comments <a class="anchor" href="#comments">🔗</a></h2><h3 id="comment-by-mike-b-on-2023-07-15-105805-0000">Comment by Mike B on 2023-07-15 10:58:05 +0000 <a class="anchor" href="#comment-by-mike-b-on-2023-07-15-105805-0000">🔗</a></h3><p>Congratulations on 25 years! Thank you for everything you have done to make my job and the jobs of many thousands easier.</p>
<h3 id="comment-by-j-zandbergen-on-2023-07-15-123853-0000">Comment by J. Zandbergen on 2023-07-15 12:38:53 +0000 <a class="anchor" href="#comment-by-j-zandbergen-on-2023-07-15-123853-0000">🔗</a></h3><p>Hi Gerald,</p>
<p>Congratulations on 25 years wireshark! Thank you so much for ~20 years of lessons learned and problems fixed!</p>
<p>Cheers!</p>
<h3 id="comment-by-dan-on-2023-07-15-151316-0000">Comment by Dan on 2023-07-15 15:13:16 +0000 <a class="anchor" href="#comment-by-dan-on-2023-07-15-151316-0000">🔗</a></h3><p>Congrats! it must take a ton of effort and motivation to keep going for 25 years!</p>
<h3 id="comment-by-john-on-2023-07-15-175758-0000">Comment by John on 2023-07-15 17:57:58 +0000 <a class="anchor" href="#comment-by-john-on-2023-07-15-175758-0000">🔗</a></h3><p>Thank you for so many fixes in many production environment because of Wireshark!</p>
<h3 id="comment-by-john-on-2023-07-15-175916-0000">Comment by John on 2023-07-15 17:59:16 +0000 <a class="anchor" href="#comment-by-john-on-2023-07-15-175916-0000">🔗</a></h3><p>*environments :)). I may need to run wireshark on my keyboard</p>
<h3 id="comment-by-teknik-industri-on-2023-07-16-171523-0000">Comment by Teknik Industri on 2023-07-16 17:15:23 +0000 <a class="anchor" href="#comment-by-teknik-industri-on-2023-07-16-171523-0000">🔗</a></h3><p>What is the significance of “Wireshark Is 25: The email that started it all and the lessons learned along the way” in relation to Wireshark?</p>
<h3 id="comment-by-nicholas-ng-on-2023-07-21-132743-0000">Comment by nicholas ng on 2023-07-21 13:27:43 +0000 <a class="anchor" href="#comment-by-nicholas-ng-on-2023-07-21-132743-0000">🔗</a></h3><p>Happy 25th birthday wirrshark</p>
