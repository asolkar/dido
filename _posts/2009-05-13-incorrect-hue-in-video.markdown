---
layout: post
status: publish
published: true
title: Incorrect hue in video?
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 198
wordpress_url: http://tech.mahesha.com/?p=198
date: '2009-05-13 11:00:11 -0700'
date_gmt: '2009-05-13 19:00:11 -0700'
categories:
- Uncategorized
tags:
- Linux
- Ubuntu
- Video
comments: []
---
<p>I was watching the<a href="http://www.apple.com/getamac/ads/" title="Apple Ads page"> Apple Get a Mac ads</a> today and this is what I got:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/movie-player-wrong-hue.png"><img src="http://tech.mahesha.com/wp-content/images/movie-player-wrong-hue.png" alt="Incorrect hue in GStreamer - Click for full size" width="475px"></a></p>
<div class="caption">Incorrect hue in videos can be corrected by fixing the hue setting in Movie Player</div>
</div>
<p>This is on Ubuntu 9.04 (Jaunty Jackalope), where Firefox uses GStreamer plug-in to display video. Movie Player (<em>Applications -> Sound &amp; Video -> Movie Player</em>) also uses GStreamer as its back-end.</p>
<p>So to fix the hue issue, I opened Movie Player preferences (<em>Edit -> Preferences</em>). In the <em>Display</em> tab, under section <em>Color Balance</em> noticed the <em>Hue</em>. In my case it was set to the minimum value. I clicked on the <em>Reset to Defaults</em> button. It reset the <em>Hue</em> slider to a center position.</p>
<p>Closed Movie Player preferences and reloaded the movie. It looked so much better.</p>
<p>Now I wonder what changed the Hue setting in the first place...</p>
