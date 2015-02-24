---
layout: post
status: publish
published: true
title: Glowy Window Shadows with Compiz
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 79
wordpress_url: http://tech.mahesha.com/2008/02/26/glowy-window-shadows-with-compiz/
date: '2008-02-26 08:15:12 -0800'
date_gmt: '2008-02-26 16:15:12 -0800'
categories:
- Uncategorized
tags:
- Ubuntu
- Technology
- Compiz
- Nvidia
- fglrx
- Hardy Heron
comments:
- id: 50
  author: Mahesh
  author_email: mahesha@mahesha.com
  author_url: http://tech.mahesha.com
  date: '2008-04-15 14:36:46 -0700'
  date_gmt: '2008-04-15 22:36:46 -0700'
  content: "Although there doesn't seem to be a fix for this yet, installing the Nvidia
    driver from Nvidia installer seems to fix the shadows.\r\n\r\n  https://bugs.launchpad.net/ubuntu/+bug/186382"
---
<p>I was running <a href="http://releases.ubuntu.com/7.10/" title="Ubuntu Linux 7.10">Ubuntu Linux 7.10 (Gutsy Gibbon)</a> on my desktop which had an ATI graphics card. There were a lot of driver related issues (<a href="http://en.wikipedia.org/wiki/Fglrx" title="Widipedia: Fglrx">fglrx driver</a>). I tried different versions of the driver, even upgraded to the alpha version of <a href="https://wiki.ubuntu.com/HardyHeron" title="Hardy Heron Alphas">Hardy Heron</a>, to gain access to the new kernel. The issues persisted. Succumbing to the driver blues, I replaced the ATI card with an <a href="http://www.nvidia.com/object/geforce_8400.html" title="GeForce 8400GS - I am no gamer">Nvidia card</a>. I am so much happier now.</p>
<p>However, I have this:</p>
<div class="img_container">
<img src="http://tech.mahesha.com/wp-content/images/compiz-nvidia-shadow-glow.png" alt="Glowy shadows"/></p>
<div class="caption">Notice the glow instead of shadow</div>
</div>
<p>What should be window shadows are somehow a glowy halo!</p>
<p>It is good to know <a href="http://bbs.archlinux.org/viewtopic.php?id=41869" title="Discussion on a similar problem">I am not the only one</a>. There's a <a href="http://bugs.opencompositing.org/show_bug.cgi?id=781" title="Bug: Inconsistent random colored window shadows">bug on CompizFusion (OpenCompositing)</a> website that tracks this issue.</p>
<p>There seems to be a general consensus that this is indeed related to the <a href="http://www.nvidia.com/object/unix.html" title="Nvidia Linux Driver page">Nvidia Linux drivers</a>.</p>
<p>Here's what is known so far. Folks dealing with glowy shadows have following in common:</p>
<ul>
<li>Some flavor of Linux (Ubuntu, ArchLinux, ...)</li>
<li>Nvidia graphics card (Mostly the 8-series)</li>
<li>Latest Nvidia driver (nvidia-glx-new version 169.09 in my case)</li>
<li>CompizFusion with <em>Window Decoration</em> plugin</li>
<li>Either Emerald or Gnome window decorator</li>
</ul>
<p>If you are dealing with similar issue, and think can add useful bit of information to the discussion, drop a comment. Better yet, update the <a href="http://bugs.opencompositing.org/show_bug.cgi?id=781" title="Bug: Inconsistent random colored window shadows">bug on CompizFusion (OpenCompositing)</a>.</p>
<p>While we are at it, is there a way of tracking bugs submitted to Nvidia (via <a href="http://www.nvidia.com/object/linux_display_ia32_169.09.html" title="<br />
Linux Display Driver - x86 Version: 169.09">nvidia-bug-report.sh</a>)?</p>
