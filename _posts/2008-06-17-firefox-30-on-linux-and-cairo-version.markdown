---
layout: post
status: publish
published: true
title: Firefox 3.0 on Linux and cairo version
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 87
wordpress_url: http://tech.mahesha.com/?p=87
date: '2008-06-17 14:54:17 -0700'
date_gmt: '2008-06-17 22:54:17 -0700'
categories:
- Uncategorized
tags:
- Linux
- Firefox
- Browser
- Ubuntu
- Hardy Heron
- Cairo
- Fonts
comments:
- id: 64
  author: me
  author_email: me@me.me
  author_url: ''
  date: '2008-08-26 07:30:18 -0700'
  date_gmt: '2008-08-26 15:30:18 -0700'
  content: The difference between the two pics is that the top one is antialiased.
    I thought you were kidding when saying that you prefered THAT to the crispy and
    clean non AA version. I spend a lot of time reading documents on my computer,
    and absolutely hate blurred fonts. Actually, I only found this entry while looking
    for ways to disable it forever.
- id: 65
  author: Mahesh
  author_email: mahesh@mahesha.com
  author_url: http://tech.mahesha.com
  date: '2008-08-26 10:55:56 -0700'
  date_gmt: '2008-08-26 18:55:56 -0700'
  content: I am not surprised. In fact, I also prefer 'crispy and clean non-AA version'
    on my laptop - it has a much better display than my desktop. May be it's the not-so-fancy
    display on my desktop that the crisp fonts don't appear so attractive. Hence I
    have to turn to anti-aliasing.
---
<p>Since its Alphas, I've been comparing font rendering in official Firefox 3.0 Linux builds and the ones I used to compile myself. Fonts in the official builds were, and still are, very crudely rendered. Upon reading a little, I learned that this difference is due to the use of different version of <a href="http://en.wikipedia.org/wiki/Cairo_(graphics)" title="Cairo - graphics">Cairo</a>, a graphics library that Firefox uses under the hood.</p>
<p>Using <code>--enable-system-cairo</code> option when building Firefox greatly improves the look of fonts. I used to compile my own nightly builds using this option, hoping that the official builds will move to using that option too, before the final 3.0 release.</p>
<p>I just tried the final release and found that it still does not use <code>--enable-system-cairo</code> option, and the fonts are still not neat.</p>
<p>Thankfully, I also noticed that Ubuntu's Firefox 3.0 - that got updated today as well, does use <code>--enable-system-cairo</code> option. Now I don't have to compile my own builds. I wish I had noticed this the first time I installed Hardy - the Firefox 3.0 beta that came with it probably used system Cairo too. But I am glad I noticed this, better late than never.</p>
<p>Here are a couple of screenshots that illustrate the difference:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/firefox-cairo-difference.png"><img src="http://tech.mahesha.com/wp-content/images/firefox-cairo-difference.png" alt="Firefox fonts with and without system cairo - Click for full size" width="475px"/></a></p>
<div class="caption">Click on the image to view full size - The one on top is the Ubuntu build, using <code>--enable-system-cairo</code> option. The one a the bottom is the official Firefox build, not using that option. Notice how the fonts in the Ubuntu build are so much better than the fonts in the official Firefox build</div>
</div>
<p>Now, go <a href="http://www.mozilla.com/en-US/firefox/all.html" title="Download Firefox 3.0">download Firefox 3.0</a> while it's hot. You don't get to set a <a href="http://www.spreadfirefox.com/en-US/worldrecord/" title="Download Day is upon us">world record</a> everyday!</p>
