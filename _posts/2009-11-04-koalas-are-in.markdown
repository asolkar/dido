---
layout: post
status: publish
published: true
title: Koalas are in!
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 307
wordpress_url: http://tech.mahesha.com/?p=307
date: '2009-11-04 13:33:00 -0800'
date_gmt: '2009-11-04 21:33:00 -0800'
categories:
- Uncategorized
tags:
- Linux
- Ubuntu
- Karmic
comments: []
---
<p>It's been around a week since <a href="http://www.ubuntu.com/news/ubuntu-910">Ubuntu 9.10 - Karmic Koala was released</a>. Both my Linux systems are now up-to-date.</p>
<p><strong>Linux systems</strong></p>
<p>One of the two machines is a Sony Vaio Laptop (VGN-T140P) and other is a desktop built on a Asus P5K-e Wifi/AP motherboard with an Nvidia 8400GS video card.</p>
<p><strong>Install strategy</strong></p>
<p>In both cases I chose to do a clean install. I always keep <code>/home</code> on a separate partition, so clean installs are not much of a hassle. I usually move all the dot-files (and directories) from <code>/home/me</code> out of the way before a clean install. After the install, I bring the ones I need manually. This, I believe, prevents any configuration issues arising from new versions of applications adding/removing/changing any configuration items. I do have to configure some applications - like compiz - all over again, but it is not a big deal most of the time.</p>
<p>I also make a copy of <code>/etc</code> directory before a clean install, just in case I need to refer to the <em>hacks</em> that worked around bugs in the previous release.</p>
<p><strong>Trends</strong></p>
<p>If I look at the way thinks are working on the two of my systems since Ubuntu 8.10 - Hardy Heron, I see pretty consistent trends. My laptop was at its best in Hardy, things are not quite that good now. The desktop, however, is at its best in Karmic! I wonder if it has to do with the video hardware (Intel in laptop, Nvidia in desktop) or wireless usage (I use it in laptop all the time, never on the desktop).</p>
<p>Suspend/resume has gotten worse on the laptop, but almost perfect on the desktop.</p>
<p>Laptop is plagued with wireless issues, but I know I am not alone there (<a href="https://bugs.launchpad.net/ubuntu/+bugs?field.searchtext=wpa&orderby=-datecreated">Launchpad bug reports as of today</a>).</p>
<p>Sound, at least on my systems, has greatly improved. It worked out of the box on both of them.</p>
<p><strong>Laptop experience</strong></p>
<p>The general feel of the <acronym title="Operating System">OS</acronym> has definitely improved. With the new boot experience, artwork, new themes, Karmic looks pretty neat. It is snappier than ever, even on the laptop with mediocre specifications. All that good stuff is marred by the issues that have come up in this release - from back in the alpha days.</p>
<p>There has always been a problem with the laptop hardware, that when it resumes from suspend (to RAM), the backlight is missing. In the past, I have been able to work around it by setting quirks in suspend/resume scripts. Those hacks don't work anymore. I haven't found any work-around for Karmic yet. <a href="https://bugs.launchpad.net/ubuntu/+source/pm-utils/+bug/417599">Launchpad bug #417599</a>. </p>
<p>An even worse issue that has come up is with the wireless networking. In my case, it just doesn't connect. Even when it does, it doesn't stay connected for long. It is extremely annoying. <a href="https://bugs.launchpad.net/ubuntu/+source/linux/+bug/429035">Launchpad but #429035</a>. So its mostly wired network for now. I know, laptop wired to the router? That sucks :(<br />
I hope not for very long though.</p>
<p><strong>Desktop experience</strong></p>
<p>On the desktop, Karmic is just sweet. Out of the box, everything just worked. Sound, video, suspend/resume, everything!</p>
<p>The only thing worth mentioning is that when I first rebooted the system after installing Karmic, Windows entry was missing from the Grub2 menu. All I did to fix this was:</p>
<pre>
  % sudo update-grub
</pre>
<p>I wonder why it missed the Windows entry during installation. I am sure it runs update-grub as an installation step, doesn't it? In any case, if you see Windows entry missing from your Grub menu after installing Karmic on a dual-boot machine, just run the above command.</p>
<p>One more thing I haven't checked is if wake-on-lan works. If it doesn't I'll need to do what I usually do after clean Ubuntu installs - <a href="http://dimmeria.com/?q=node/1755">Howto: Wake on LAN with ASUS P5WDG2 WS Pro in Debian/Ubuntu</a>. Hope it works this time too!</p>
<p>Well, there. Now that the computer are all working, time to get some work done!</p>
<p>Incidentally, I set up a <a href="https://github.com/">github</a> account for all my little hobby projects. <a href="http://github.com/asolkar">Check it out</a>. All the projects are purely experimental and educational. Nothing is going to blow your mind.</p>
