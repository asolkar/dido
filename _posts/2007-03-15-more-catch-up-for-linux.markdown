---
layout: post
status: publish
published: true
title: More catch-up for Linux
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 20
wordpress_url: http://tech.mahesha.com/2007/03/15/more-catch-up-for-linux/
date: '2007-03-15 17:08:44 -0700'
date_gmt: '2007-03-16 01:08:44 -0700'
categories: []
tags:
- OS
- Linux
comments: []
---
<p>During a recent trip, I realized - again - that Linux still has a lot of catch-up to play on user experience front. I traveled with a Ubuntu 6.10/XP dual-boot laptop and a lot of times, I had to fall back on XP to get things done.</p>
<p><strong>Wireless connection at Frankfurt airport</strong></p>
<p>Getting a paid wireless connection at Frankfurt airport is easy. Just join one of the available open wireless networks, it takes you to a website where you can pay for the connection and you are all set. I could do this in no time with XP.</p>
<p>Although I first tried this with Ubuntu. The troubles started with the fact that in order to setup a wireless connection I need to know the name of the network to join. I really prefer the windows way where the wireless network setup process starts with a list of available networks. Then at least you are not lost to begin with. I talked with a neighboring traveler who was using a Mac. He did not have trouble getting on to a network - because the Mac connected to an available open network since none of the preferred networks were found. That works too. In any case, I was stuck and ended up using XP to get connected.</p>
<p>Once connected, I tried to find some information on this situation. Turns out that there are packages available via the Package Manager that can help - notably, the <a href="http://wifi-radar.systemimager.org/" title="wifi-radar webpage">wifi-radar</a> and <a href="http://www.gnome.org/projects/NetworkManager/">NetworkManager</a>. After getting back from the trip, I tried both. I like NetworkManager and am using it right now. It has made connecting to networks so much easier. I wonder why such a useful package is not installed by default!</p>
<p><strong>Using the modem</strong></p>
<p>Another instance where I had to go back to XP. It's simple in XP all you need to know is the phone number to dial, a username and a password. <em>Start</em> -> <em>Connect To</em> -> <em>Connection Name</em> - enter the information and you are online. Why can't it be the case in Linux?</p>
<p>I read a little bit in order to understand what's missing in my installation and how I could get the modem going. It involved stuff about <code>pppd</code>, using <em>scanModem</em> utility, editing a bunch of root-owned files - things if I told my mother, she's vow not to use the computer again.</p>
<p>Things gotta be easier than this. I am still trying to find an easier way to get the modem working. If I find something, I'll update this post.</p>
