---
layout: post
status: publish
published: true
title: Install Jolicloud without USB boot support (with PLoP)
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 241
wordpress_url: http://tech.mahesha.com/?p=241
date: '2009-07-30 07:50:36 -0700'
date_gmt: '2009-07-30 15:50:36 -0700'
categories:
- Uncategorized
tags:
- jolicloud
- bootmanager
- PLoP
comments:
- id: 777
  author: Jolicloud &amp; Linux dual boot?
  author_email: ''
  author_url: http://www.therevcounter.com/technology-computing-gadgetry/60835-jolicloud-linux-dual-boot.html#post1256212
  date: '2010-12-16 10:40:23 -0800'
  date_gmt: '2010-12-16 18:40:23 -0800'
  content: '[...]  [...]'
- id: 906
  author: Anand
  author_email: anandjoth@hotmail.com
  author_url: ''
  date: '2010-12-22 08:08:50 -0800'
  date_gmt: '2010-12-22 16:08:50 -0800'
  content: 'Thanks Mahesh. This is exactly the thing I&#039;m looking for. '
---
<p><a href="http://www.jolicloud.com/" title="Jolicloud website">Jolicloud</a>, in their own words, is <em>a cool new OS</em>. It is mainly targeted towards netbooks and other small laptop devices. It is currently in an invitation only private alpha. You can get an invite by <a href="http://my.jolicloud.com/account/invitation?next=/register" title="Jolicloud registration page">registering on their website</a>. I was lucky enough to get an invite last week.</p>
<p>I spent almost entire last week, in trying to install it on my Sony VAIO VGN-T140P laptop. It is a small laptop, so I thought Jolicloud would be a good option to try. However, the laptop BIOS does not support booting from a USB drive. And Jolicloud only provides a <code>.img</code> file that can go on a USB drive.</p>
<p>During the past week, I tried various ways to convert the <code>.img</code> file into a good <code>.iso</code> file that I can burn onto a CD and boot from there - sadly to no avail. Among the many things I tried were <code>ccd2iso</code>, <code>nrg2iso</code>, <code>mkisofs</code>, plain renaming of the <code>.img</code> file to a <code>.iso</code> file. Nothing generated a CD that I could boot from. All I had was a full set of 12 bad-CD coasters!</p>
<p>Last night, I found another free product that made me say <strong>WOW!</strong> aloud! During some intense <em>googling</em>, I came across this thing called <a href="http://www.plop.at/en/bootmanager.html" title="PLoP Bootmanager website">PLoP Bootmanager</a>. It claimed to do exactly what I wanted - boot from USB without the support from BIOS! I downloaded it and put it on a CD. With the Jolicloud USB drive in the USB port and PLoP Bootmanager CD in the CD drive, I restarted this laptop - it worked! PLoP Bootmanager came up, and showed me an option to boot from USB! I selected it and <em>woo hoo!</em> Jolicloud was booting!</p>
<p>I've installed Jolicloud on this laptop since, and am liking it. My laptop is not one of the supported devices, so I am sure there will be problems, but none so far. In fact, I am posting this from Google Chrome installed via Jolicloud Applications.</p>
<p>There are a few software titles that I swear by and always keep a copy handy - <a href="http://www.supergrubdisk.org/" title="SuperGrubDisk home page">SuperGrubDisk</a>, <a href="http://gparted.sourceforge.net/" title="GParted page">GParted</a>, <a href="http://ubuntu.com/" title="Ubuntu website">Ubuntu on a USB drive</a> - to name a few. From today, I am keeping <a href="http://www.plop.at/en/bootmanager.html" title="PLoP Bootmanager website">PLoP Bootmanager CD</a> in that bag of goodies too! Kudos and many thanks to PLoP devs!</p>
