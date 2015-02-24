---
layout: post
status: publish
published: true
title: Chrome and LibreOffice on RHEL 6.1
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 561
wordpress_url: http://tech.mahesha.com/?p=561
date: '2011-12-15 21:59:32 -0800'
date_gmt: '2011-12-16 05:59:32 -0800'
categories:
- Uncategorized
tags:
- Linux
- Pidgin
- LibreOffice
- Chrome
- RHEL
comments: []
---
<p>So there is this Red Hat Enterprise Linux (RHEL) 6.1 machine I have. I do not have administrative rights on it. Albeit for a good reason, it makes life very inconvenient. Especially as compared to this another Ubuntu/Debian machine where I have full access.</p>
<p>RHEL 6.1 comes with tools that are, well, dated. So I tend to install the later versions of tools I use regularly. Some of the easy ones include <a href="http://nightly.mozilla.org" title="Firefox nightly builds" target="_blank">Firefox</a>, <a href="http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/latest-comm-central/" title="Thunderbird nightly builds" target="_blank">Thunderbird</a>, <a href="http://gpodder.org/downloads" title="gPodder downloads" target="_blank">gPodder</a> and <a href="http://get.adobe.com/reader/otherversions/" title="Adobe reader" target="_blank">Adobe Reader</a>. These are easy, because the vendors provide simple 'tar.gz' packages that I can just inflate and use.</p>
<p>Then there are applications like <a href="http://pidgin.im/download/" title="Pidgin downloads" target="_blank">Pidgin</a>, <a href="http://xmms2.org/wiki/Download_XMMS2" title="XMMS2 downloads" target="_blank">XMMS2</a> and <a href="http://sourceforge.net/projects/re-alpine/" title="re-alpine downloads" target="_blank">re-alpine</a> which can be easily compiled from source.</p>
<p>And then there are applications like Google Chrome and LibreOffice which I always want to install. But since they come in RPM packages, installing them without root privileges is next to impossible... or so I thought.</p>
<p><b>Chrome</b></p>
<p>Until recently I was using <a href="http://www.cs.bham.ac.uk/~cxs548/chrome" title="Chromium build" target="_blank">Chris Staite's Chromium build</a>. It works well, only it was stuck at version 14.</p>
<p>So I decided to try my luck and inflate the <a href="http://www.google.com/chrome/intl/en/eula_beta.html?dl=beta_amd64_rpm" title="64-bit Chrome Beta" target="_blank">official Google Chrome RPM</a>. So I did the following:</p>
<p>{% gist asolkar/1484599 Chrome Installation.csh %}</p>
<p>This creates a directory structure under <code>/one/of/my/dirs</code> with chrome installed at <code>/one/of/my/dirs/sys/opt/google/chrome/google-chrome</code>.</p>
<p>Now, either this process is <i>supposed</i> to work, or I was incredibly lucky. But once I pointed <code>LD_LIBRARY_PATH</code> appropriately, chrome launches and works fine! Here's the launcher I use:</p>
<p>[gist https://gist.github.com/asolkar/1484599 file="chrome-starter.csh" /]</p>
<p>Chrome requires that the <code>chrome-sandbox</code> binary in the Chrome installation directory be installed as root. In my case, this is not the case. So Chrome refuses to launch with sandbox enabled. That is the reason for the <code>--no-sandbox</code>. Obviously, there are security repercussions, and Chrome warns you about that every time it is launched.</p>
<p><b>LibreOffice</b></p>
<p>This success in installation of Chrome totally boosted my confidence! So I decided to take a stab at that other application that I always wanted to be up-to-date - LibreOffice. Turns out it is easier than Chrome!</p>
<p>All it takes is <a href="http://www.libreoffice.org/download/" title="Get LibreOffice" target="_blank">downloading the right RPMS</a> and inflating them into the same <code>/one/of/my/dirs</code> directory!</p>
<p>[gist https://gist.github.com/asolkar/1484599 file="LibreOffice Installation.bash" /]</p>
<p>And that is it, LibreOffice is installed at <code>/one/of/my/dirs/sys/opt/libreoffice3.4/program/soffice</code>!</p>
<p>Like I said, I am not sure this process is supposed to work, but it did beautifully in my case!</p>
