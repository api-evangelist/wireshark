---
title: "What’s New In Wireshark 4.0?"
url: "https://blog.wireshark.org/2022/10/whats-new-in-wireshark-4-0/"
date: "Tue, 04 Oct 2022 23:22:08 +0000"
author: ""
feed_url: "https://blog.wireshark.org/index.xml"
---
<p>Wireshark 4.0 was released today, and as you might have guessed from the version number, quite a few things have changed since 3.6. If you are a regular Wireshark user we recommend that you pay close attention to the <a href="https://www.wireshark.org/update/relnotes/wireshark-4.0.0.html">release notes</a> this time around, since it includes quite a few changes. I’ll cover some highlights here, but the release notes go into much greater detail.</p>
<h2 id="_display_filter_changes.wp-block-heading">Display Filter Changes <a class="anchor" href="#_display_filter_changes.wp-block-heading">🔗</a></h2><p><a href="https://www.wireshark.org/docs/man-pages/wireshark-filter.html">Display filters</a> are one of Wireshark’s defining features and 4.0 makes them more powerful and more consistent. These improvements give you more control over the way that multiple occurrences of the same field are handled, let you do arithmetic, and many other things.</p>
<p>First, let’s look at the way multiple field occurrences are handled. Suppose you want to filter on an IPv4 source address. Within Wireshark that means using the “ip.src” filter field. You might assume that the packets on your network have one IPv4 header and therefore one source address, but that’s not necessarily the case. You might be in an environment that uses some form of tunneling like GRE or one of the many VPN protocols, and even on simple networks ICMP errors carry the IPv4 header of the offending packet. Maybe you live on the edge and used <a href="https://scapy.net/">scapy</a> to create a packet with a hundred or a thousand layers of IP in IP nesting.</p>
<p>In any case a filter like “ip.src == 10.1.2.3” can be ambiguous. Even worse, Wireshark has a completely made up “ip.addr” field, which is an alias for both “ip.src” and “ip.dst”. It’s convenient, but it also means you’re guaranteed to have two “ip.addr” fields for each IPv4 header which means guaranteed ambiguity.</p>
<p>In order to reduce this ambiguity Wireshark 4.0 adds a <em>layer operator</em>, which lets you select a specific occurrence of a field. To use the layer operator, just put a number sign and a layer number after a field. For example, if we have a GRE packet with both outer and inner IPv4 layers,</p>
<pre class="wp-block-preformatted">ip.src#1 == 10.1.2.3</pre>
<p>will match the outer address,</p>
<pre class="wp-block-preformatted">ip.src#2 == 10.1.2.3</pre>
<p>will match the inner address, and</p>
<pre class="wp-block-preformatted">ip.src == 10.1.2.3</pre>
<p>will match either address.</p>
<p>Along with layers, you can be much more specific about matching zero, one or more, or all fields in a particular packet. You have been able to do the following comparison operators since Wireshark’s inception:</p>
<pre class="wp-block-preformatted">ip.addr == 10.100.100.1</pre>
<p>If <em>any</em> of these match, we have a winner.</p>
<pre class="wp-block-preformatted">not ip.addr == 10.100.100.1</pre>
<p>If <em>none</em> of these match we have a winner.</p>
<p>Wireshark also has “!=” (not equal), which was a bit confusing in past versions. This was fixed in Wireshark 3.6:</p>
<pre class="wp-block-preformatted">ip.addr != 10.100.100.1</pre>
<p>In Wireshark 3.4 and earlier, if any of these <em>don’t</em> match, we have a winner. In Wireshark 3.6 and later, if <em>none of these</em> match, we have a winner.</p>
<p>Wireshark 4.0 adds the following:</p>
<pre class="wp-block-preformatted">ip.addr any_eq 10.100.100.1</pre>
<p>If <em>any</em> of these match, we have a winner, similar to “==”.</p>
<pre class="wp-block-preformatted">ip.addr all_ne 10.100.100.1</pre>
<p>If <em>none</em> of these match, we have a winner, similar to “!=” in version 3.6 and later.</p>
<pre class="wp-block-preformatted">ip.addr === 10.100.100.1<br />ip.addr all_eq 10.100.100.1</pre>
<p>If <em>all</em> addresses match, we have a winner.</p>
<pre class="wp-block-preformatted">ip.addr !== 10.100.100.1<br />ip.addr any_ne 10.100.100.1</pre>
<p>If <em>any</em> addresses <em>don’t</em> match, we have a winner, similar to “!=” in version 3.4 and earlier.</p>
<p>You can also do arithmetic – you can add, subtract, multiply, and divide. You can use the modulo (%) operator, which gives you the remainder of integer division. Suppose your company has all of its web servers running on a port that ends in 443: 443, 1443, 5443, 21443, etc. You can use the modulo operator to match them like so:</p>
<pre class="wp-block-preformatted">{tcp.port % 1000} == 443</pre>
<p>There are a bunch of other changes as well. You can now match bytes starting from the end of a PDU, dates and times can be specified as UTC, Unicode can be matched using code points,</p>
<h2 id="_default_main_window_layout.wp-block-heading">Default main window layout <a class="anchor" href="#_default_main_window_layout.wp-block-heading">🔗</a></h2><p>In past releases Wireshark followed a standard set by its predecessors and placed the packet list, packet detail, and byte view on top of each other, like so:<figure class="wp-block-image size-large"></p>
<p><img alt="" class="wp-image-780" height="709" src="https://blog.wireshark.org/wp-content/uploads/2022/10/layout-old-1024x709.png" width="1024" /> </figure></p>
<p>That standard was set a long time ago when most monitors had a 4:3 aspect ratio and lower resolutions than they do these days. As of Wireshark 4.0, the default is for the detail and byte view to be next to each other, which makes it easier to take advantage of the real estate available on modern displays:<figure class="wp-block-image size-large"></p>
<p><img alt="" class="wp-image-781" height="709" src="https://blog.wireshark.org/wp-content/uploads/2022/10/layout-new-1024x709.png" width="1024" /> </figure></p>
<h2 id="_conversations_and_endpoints.wp-block-heading">Conversations and Endpoints <a class="anchor" href="#_conversations_and_endpoints.wp-block-heading">🔗</a></h2><p>The Conversations and Endpoints dialogs have been a popular feature for a long time and are often the first place people look when investigating a problem. Wireshark 4.0 makes them more powerful and easier to use. For example, you can tear off tabs — you can now see TCP and UDP conversations side by side in separate windows. Sorting has been improved, you can now hide columns, filter on stream IDs, and export data as JSON.<figure class="wp-block-image size-large"></p>
<p><img alt="" class="wp-image-782" height="546" src="https://blog.wireshark.org/wp-content/uploads/2022/10/conv-dialog-1024x546.png" width="1024" /> </figure></p>
<h2 id="_hex_import.wp-block-heading">Hex import <a class="anchor" href="#_hex_import.wp-block-heading">🔗</a></h2><p>Sometimes the packets you’re interested in aren’t in a nice pcap or pcapng file that you can just open with Wireshark, and are instead buried in a hex dump. Wireshark provides two ways to convert hex dumps to pcaps: “Import From Hex Dump” in the main application and the <code>text2pcap</code> utility. They had different feature sets and behaved differently in past versions, but they are much more consistent in Wireshark 4.0.</p>
<h2 id="_whats_going_away.wp-block-heading">What’s Going Away <a class="anchor" href="#_whats_going_away.wp-block-heading">🔗</a></h2><p>We no longer ship official 32-bit Windows packages for Wireshark 4.0 and later. If you’re still using a 32-bit Windows system, we’ll keep shipping Wireshark 3.6 updates until 2024. You won’t be able to take advantage of the cool new features in 4.0 and later, unfortunately.</p>
<h2 id="_whats_not_here_yet.wp-block-heading">What’s Not Here Yet <a class="anchor" href="#_whats_not_here_yet.wp-block-heading">🔗</a></h2><p>There are two features for Windows that we’d really like to add, but didn’t make the cut for 4.0: Dark mode and Arm64 support. Dark mode requires support from Qt, our user interface library. It’s still a <a href="https://bugreports.qt.io/browse/QTBUG-72028">work in progress</a>, but we’re hoping it will make its way into Wireshark 4.2.</p>
<p>Building packages for Arm64 requires build hardware and software library support. We hope to have both of those in place for Wireshark 4.2 as well.</p>
<h2 id="_if_youre_a_developer.wp-block-heading">If You’re A Developer <a class="anchor" href="#_if_youre_a_developer.wp-block-heading">🔗</a></h2><p>We now require a C11 compiler, the PCRE2 library, and updated versions of many of the third party libraries that we use. We no longer require Perl to build Wireshark.</p>
<h2 id="_summary.wp-block-heading">Summary <a class="anchor" href="#_summary.wp-block-heading">🔗</a></h2><p>There are a bunch of other new features and improvements coming your way in Wireshark 4.0. Thanks to all of the developers that helped make this happen!</p>
<h2 id="comments">Comments <a class="anchor" href="#comments">🔗</a></h2><h3 id="comment-by-guy-harris-on-2022-10-05-063519-0000">Comment by Guy Harris on 2022-10-05 06:35:19 +0000 <a class="anchor" href="#comment-by-guy-harris-on-2022-10-05-063519-0000">🔗</a></h3><p>Note that “Arm64 support” here specifically refers to Windows binary packages distributed from wireshark.org.</p>
<p>If, for example, a Linux distribution supports Arm64, they may provide Arm64 packages, whether source or binary, for current or past Wireshark versions. The issue is, as Gerald noted, an issue of wireshark.org building binary packages.</p>
<p>Furthermore, we already provide Arm64 binary packages of Wireshark 3.6.8 and, now, 4.0 for macOS.</p>
<h3 id="comment-by-kara-on-2022-10-05-145209-0000">Comment by Kara on 2022-10-05 14:52:09 +0000 <a class="anchor" href="#comment-by-kara-on-2022-10-05-145209-0000">🔗</a></h3><p>Good</p>
<h3 id="comment-by-totzi-on-2022-10-26-081458-0000">Comment by Totzi on 2022-10-26 08:14:58 +0000 <a class="anchor" href="#comment-by-totzi-on-2022-10-26-081458-0000">🔗</a></h3><p>YEAY!</p>
