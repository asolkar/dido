---
layout: post
status: publish
published: true
title: Chrome OS in VirtualBox
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 318
wordpress_url: http://tech.mahesha.com/?p=318
date: '2009-11-20 23:19:41 -0800'
date_gmt: '2009-11-21 07:19:41 -0800'
categories:
- Uncategorized
tags:
- Google
- Chrome OS
- VirtualBox
- Chromium
comments:
- id: 414
  author: Day in, day out&#8230; &raquo; Blog Scare and Chrome OS Update
  author_email: ''
  author_url: http://tech.mahesha.com/2009/11/25/blog-scare-and-chrome-os-update/
  date: '2009-11-25 00:13:31 -0800'
  date_gmt: '2009-11-25 08:13:31 -0800'
  content: '[...] my last post about running Chrome OS in VirtualBox, there are some
    screenshots. As you can see, the default screen size of 800x600 is pretty tiny
    to [...]'
- id: 699
  author: Day in, day out&#8230; &raquo; What do I think of the Cr-48?
  author_email: ''
  author_url: http://tech.mahesha.com/2010/12/11/what-do-i-think-of-the-cr-48/
  date: '2010-12-11 15:44:16 -0800'
  date_gmt: '2010-12-11 23:44:16 -0800'
  content: '[...] OS has evolved very well. I played with it a bit in VirtualBox when
    it was initially announced about a year ago. But the user experience of Chrome
    OS on Cr-48 is [...]'
---
<p>Ever since they made the <a href="http://www.chromium.org/chromium-os">Chromium source</a> code public yesterday morning, I've been itching to build it and take it for a spin. I did not know it would take only a couple hours to do that!</p>
<p><strong>Getting and Building</strong></p>
<p>I am so impressed! The instructions on the <a href="http://www.chromium.org/chromium-os/building-chromium-os">Getting and Building a Chromium-Based OS</a> page are precise, to-the-point and.. they work! I am not sure if this is brilliant scripting, great documentation, me having just right prerequisites (Ubuntu Karmic Koala), or a combination of all these. But it took me just over an hour or so to download source and build a '<code>.vmdk</code>' file for VirtualBox. I did not see that coming.</p>
<p>I've built other projects from source before. It always involves some <em>figuring-out</em>. Sometimes the documentation is not adequate - may be inadequate for my skill-set. Sometimes the prerequisites are not clearly specified/checked. Building an entire OS, I was preparing for a few days of reading up and figuring things out.</p>
<p>But it was none of that. I just followed the steps - mostly word-to-word - and I had a virtual disk image (<code>.vmdk</code> file) at the end of it all!</p>
<p>The only change I had to do was to <code>BASE_FROM</code> in <code>~/chromiumos/src/platform/chrome/copy_chrome_zip.sh</code> to use <code>build.chormium.org</code> instead of <code>chrome-web</code>. I think this was because I chose not to build Chromium (browser) from source. I am sure this will be ironed out soon (may be it is already).</p>
<p><strong>Using in VirtualBox</strong></p>
<p>I followed the instructions to <a href="http://sites.google.com/a/chromium.org/dev/chromium-os/building-chromium-os/build-instructions#TOC-Convert-the-image-for-VMWare">Convert the image for VMWare</a>, which creates a <code>.vmdk</code> file. Instead of using VMWare workstation, I used VirtualBox to fire it up.</p>
<p><strong>Impressions</strong></p>
<p>I love the concept of Google Chrome OS. I think it is very relevant to how we use the computer these days. It would be even better if Chrome OS would coexist with a normal OS on any laptop. I agree that most often we only use the computer to access the web and do most of our things on the Internet. But I am not ready to give up the full-fledged OS, not quite yet. Does that remind me of <a href="http://www.splashtop.com/splashtop_overview.php">SplashTop</a>?</p>
<p>Here are a couple of obligatory screenshots:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/ChromiumOS.png" ><img src="http://tech.mahesha.com/wp-content/images/ChromiumOS.png" alt="Woo hoo! Build worked!" width="500px"/></a></p>
<div class="caption">Chromium OS build in VirtualBox, running Google Wave</div>
</div>
<p>Following is the list of Apps currently on the home page. These showed up only today. Yesterday when I was trying the OS for the first time, one could only use @google.com usernames to sign in. I am sure things are going to be changing fast in the next weeks/months.</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/ChromiumOS_apps.png" ><img src="http://tech.mahesha.com/wp-content/images/ChromiumOS_apps.png" alt="Apps on Chromium OS home page" width="500px"/></a></p>
<div class="caption">Apps on Chromium OS home page</div>
</div>
<p><strong>Next...</strong></p>
<p>Next thing I am going to try is to get hold of a 4GB USB drive and see if this image works on my laptop.</p>
<p>Secondly, I am curious to see if the OS updates itself in the VirtualBox, like Google has mentioned. If it does, I should not be required to build another image... ever!</p>
<p>Back to more experiments.</p>
<p>Later...</p>
