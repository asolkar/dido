---
layout: post
status: publish
published: true
title: Blog Scare and Chrome OS Update
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 327
wordpress_url: http://tech.mahesha.com/?p=327
date: '2009-11-25 00:13:24 -0800'
date_gmt: '2009-11-25 08:13:24 -0800'
categories:
- Uncategorized
tags:
- WordPress
- Chrome OS
- VirtualBox
comments:
- id: 416
  author: Twitted by twitanium
  author_email: ''
  author_url: http://realurl.org/twitted.php?id=6044663704
  date: '2009-11-25 00:29:20 -0800'
  date_gmt: '2009-11-25 08:29:20 -0800'
  content: '[...] This post was Twitted by twitanium [...]'
---
<p>Today I had a kind of a scare. This morning, I noticed that this blog was down. My first guess was that it should probably be related to the <a href="http://www.dreamhoststatus.com/2009/11/24/network-failure/">intermittent outages my host was facing</a>.</p>
<p>The blog was sending back <a href="http://pcsupport.about.com/od/findbyerrormessage/a/500servererror.htm"><em>500 - Internal Server Error</em></a> responses. The <code>error.log</code> file was filled with messages like these:</p>
<pre>
[Tue Nov 24 10:38:42 2009] [error] [client 149.117.7.28] Premature end of script headers: index.php
[Tue Nov 24 10:39:23 2009] [error] [client 149.117.7.28] Premature end of script headers: index.php
[Tue Nov 24 10:41:05 2009] [error] [client 209.85.238.214] Premature end of script headers: index.php
[Tue Nov 24 10:41:46 2009] [error] [client 209.85.238.214] Premature end of script headers: index.php
</pre>
<p>As usual, I looked for help on the <a href="http://wordpress.org/support/topic/335244">WordPress Forums</a>. When the initial suggestions did not resolve the problem, I decided to dig deeper. I downloaded WordPress and extracted a clean install. All I did was moved over this blog's <code>wp-config.php</code> into this directory. It again resulted in the same <em>500 - Internal Server Error</em> response. That almost certainly indicated a corrupt database.</p>
<p>Thankfully, reverting to the last good backup is fairly easy in <a href="http://panel.dreamhost.com/">DreamHost Panel</a>. The <em>Restore DB</em> option is available under <em>Actions</em> for each database in the <em>Main Menu &rarr; MySQL Databases</em> section of the panel. After restoring the database, the blog was back up and running.</p>
<p>Now, only thing bothering me is - what caused the database corruption? Was it some server glitch, that would hopefully never happen again? Was it a plugin (like <a href="http://intensedebate.com/">IntenseDebate</a>, etc.) that misbehaved? Or a blog management client (like <a href="http://blackberry.wordpress.org/">WordPress for BlackBerry</a>, etc.)? Not sure. But the mystery does make me nervous. But for the time being, things look OK!</p>
<p><strong>Chrome OS Update</strong></p>
<p>In my last post about running <a href="http://tech.mahesha.com/2009/11/20/chrome-os-in-virtualbox/">Chrome OS in VirtualBox</a>, there are some screenshots. As you can see, the default screen size of <code>800x600</code> is pretty tiny to do anything useful.</p>
<p>To increase the screen size, I tried two ways I would have tried for any other Linux guest:</p>
<ul>
<li><a href="http://www.nerdgrind.com/how-to-increase-screen-size-or-resolution-in-virtualbox-for-ubuntu-or-linux/">Guest Additions</a></li>
<li><a href="http://www.ghacks.net/2009/02/04/get-to-know-linux-understanding-xorgconf/">Customize <code>/etc/X11/xorg.conf</code></a></li>
</ul>
<p>Not sure why, but I could not install any Guest Additions to the Chrome OS running as guest.</p>
<p>I tried to update <code>/etc/X11/xorg.conf</code> to define screen modes (by first dropping to a shell using <strong><code>ALT + CTRL + t</code></strong> - which, by the way, does not always work for me :( ). But Chrome OS would not let me save the <code>/etc/X11/xorg.conf</code>, even with <code>sudo</code>. Is this normal?</p>
<p>In any case, I had to take the long route. Updating <code>~/chromiumos/src/rootfs_static_data/common/etc/X11/xorg.conf</code> and re-building the image. But it worked! Now I am running Chrome OS in <code>1024x768</code> mode, which is so much better!</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/ChromiumOS_1024x768.png"><img src="http://tech.mahesha.com/wp-content/images/ChromiumOS_1024x768.png" alt="Chromium OS in VirtualBox in 1024x768 mode" width="500px"></a></p>
<div class="caption">Chromium OS build in VirtualBox, running Google Wave is so much better at 1024x768</div>
</div>
<p>That is it for now...</p>
