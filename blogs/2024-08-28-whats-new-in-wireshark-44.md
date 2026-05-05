---
title: "What’s New In Wireshark 4.4?"
url: "https://blog.wireshark.org/2024/08/whats-new-in-wireshark-4-4/"
date: "Wed, 28 Aug 2024 21:05:31 +0000"
author: ""
feed_url: "https://blog.wireshark.org/index.xml"
---
<p>Wireshark 4.4.0 has been released and it includes a lot of improvements and updates since version 4.2.0 was released last November.
I’ll cover some highlights here, but you will definitely want to check out the <a href="https://www.wireshark.org/docs/relnotes/wireshark-4.4.0">release notes</a><sup id="fnref:1"><a class="footnote-ref" href="#fn:1">1</a></sup> for details.</p>
<h2 id="graph-dialogs">Graph Dialogs <a class="anchor" href="#graph-dialogs">🔗</a></h2><p>Many bugs have been fixed in the graph dialogs (I/O Graphs, Sequence Diagrams, and TCP Stream Graphs), and performance has been improved.</p>
<p>The following improvements have been made to the I/O Graphs dialog:</p>
<ul>
<li>The minimum interval is now 1 microsecond.</li>
<li>The Y axis now uses SI prefixes.</li>
<li>Bar graphs are rendered more sensibly.</li>
<li>The graph list can be reordered by dragging and dropping items.</li>
<li>Graph legends and layer orders always match the graph list order.</li>
<li>The legend can be moved by right-clicking on it.</li>
</ul>
<figure>
    <img alt="The new bar graphs and intervals" src="https://blog.wireshark.org/images/wireshark-4-4-io-graphs.png" /><figcaption>The new bar graphs and intervals</figcaption></figure><p>The Sequence Diagram (Flow Graphs and VoIP Calls) dialog has been improved as well:</p>
<ul>
<li>The entire graph can be exported as an image.
Previously, only the items on screen were exported.</li>
<li>Endpoints with the same address are now displayed correctly.</li>
</ul>
<p>The TCP Stream Graphs dialog does a better job of identifying the client and server sides of connections.</p>
<h2 id="custom-columns">Custom Columns <a class="anchor" href="#custom-columns">🔗</a></h2><p>You can now add custom columns that do the following:</p>
<ul>
<li>
<p>Use arithmetic.
For example, <code>frame.len * 8</code> will show the frame length in bits instead of bytes.</p>
</li>
<li>
<p>Show the raw bytes of fields using the <code>@</code> operator.
For example, <code>@ip.src</code> will show the raw bytes of the IPv4 source address.</p>
</li>
<li>
<p>Logical tests like <code>tcp.port == 443</code> will show a check mark in the column when the check matches.</p>
</li>
</ul>
<h2 id="other-updates">Other Updates <a class="anchor" href="#other-updates">🔗</a></h2><p>There are a whole bunch of display filter updates and improvements.
If you&rsquo;re a power user you will definitely want to check them out.</p>
<p>The &ldquo;Follow Stream&rdquo; dialog can now show delta times and turns.</p>
<p>You can now add a display filter to a configuration profile.
When you open a capture file, Wireshark will automatically switch to that profile if the filter matches.</p>
<figure>
    <img alt="Automatic profile switching" src="https://blog.wireshark.org/images/wireshark-4-4-auto-profile.png" /><figcaption>Automatic profile switching</figcaption></figure><h2 id="links">Links <a class="anchor" href="#links">🔗</a></h2><div class="footnotes">
<hr />
<ol>
<li id="fn:1">
<p>The complete Wireshark 4.4.0 release notes can be found at <a href="https://www.wireshark.org/docs/relnotes/wireshark-4.4.0.html">https://www.wireshark.org/docs/relnotes/wireshark-4.4.0.html</a>&#160;<a class="footnote-backref" href="#fnref:1">&#x21a9;&#xfe0e;</a></p>
</li>
</ol>
</div>
