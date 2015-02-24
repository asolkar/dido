---
layout: post
status: publish
published: true
title: Conky with XMMS2 on Ubuntu 10.04 (Lucid Lynx)
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 366
wordpress_url: http://tech.mahesha.com/?p=366
date: '2010-05-30 18:59:05 -0700'
date_gmt: '2010-05-31 02:59:05 -0700'
categories:
- Uncategorized
tags:
- Ubuntu
- Conky
- XMMS2
comments:
- id: 612
  author: Zac
  author_email: zrb0529@gmail.com
  author_url: ''
  date: '2010-07-18 20:07:44 -0700'
  date_gmt: '2010-07-19 04:07:44 -0700'
  content: 'Hey, I was wondering, if I already installed  conky (sudo apt-get install
    conky) how should I go about building conky to support xmms2 ? :)  Thanks! '
- id: 613
  author: Mahesh Asolkar
  author_email: mahesh@mahesha.com
  author_url: http://intensedebate.com/people/asolkar
  date: '2010-07-19 04:43:23 -0700'
  date_gmt: '2010-07-19 04:43:23 -0700'
  content: 'Yes. I believe that the default conky installed via Ubuntu repositories
    does not have XMMS2 support built in. You can tell if you run the command &#039;conky
    -v&#039; in Terminal. If you see XMMS2 under &#039;Music detection&#039; section
    conky supports XMMS2. If it does not, you will have top build it with the &#039;--enable-xmms2&#039;
    option as discussed in the post. '
---
<p>Default <a href="http://conky.sourceforge.net/" target="_blank">Conky</a> in Ubuntu 10.04 (Lucid Lynx) does not come with <a href="http://xmms2.org/wiki/Main_Page" target="_blank">xmms2</a> support built in. Since I use xmms2 extensively, building conky from source was the only option. Here's how I did it:</p>
<p><script src="http://gist.github.com/418822.js?file=conky_lucid.sh"></script></p>
<p>That should install Conky with xmms2 support in <code>/opt/conky</code>. And here's the obligatory screen shot:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/xmms2_conky.png"><img src="http://tech.mahesha.com/wp-content/images/xmms2_conky.png" alt="XMMS2 music display with Conky - Click for full size" width="525px"></a></p>
<div class="caption">XMMS2 music display with Conky</div>
</div>
<p>Just for reference, here's the <code>conkyrc</code> I use for music:</p>
<p><script src="http://gist.github.com/418820.js?file=music.conkyrc.sh"></script></p>
<p>Happy listening!</p>
