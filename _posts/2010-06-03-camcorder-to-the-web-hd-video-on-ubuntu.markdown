---
layout: post
status: publish
published: true
title: Camcorder to the Web - HD Video on Ubuntu
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 371
wordpress_url: http://tech.mahesha.com/?p=371
date: '2010-06-03 06:52:15 -0700'
date_gmt: '2010-06-03 14:52:15 -0700'
categories:
- Uncategorized
tags:
- Linux
- Ubuntu
- OpenShot
- PiTiVi
- Video Editing
- featured
comments:
- id: 578
  author: Tweets that mention Day in, day out… » Camcorder to the Web – HD Video on
    Ubuntu -- Topsy.com
  author_email: ''
  author_url: http://topsy.com/trackback?utm_source=pingback&amp;utm_campaign=L2&amp;url=http://tech.mahesha.com/2010/06/03/camcorder-to-the-web-hd-video-on-ubuntu/
  date: '2010-06-03 07:38:20 -0700'
  date_gmt: '2010-06-03 15:38:20 -0700'
  content: '[...] This post was mentioned on Twitter by Mahesh Asolkar, Mahesh Asolkar.
    Mahesh Asolkar said: New blog post: Camcorder to the Web – HD Video on Ubuntu|http://ow.ly/1TAoa
    . What are your experiences with Linux video editors? [...]'
- id: 579
  author: Hitachi DZ-HV575E pocket camcorder unboxing | Shoot &amp; Share Video Camera
  author_email: ''
  author_url: http://shootandsharecamera.com/news/hitachi-dz-hv575e-pocket-camcorder-unboxing/
  date: '2010-06-03 08:47:19 -0700'
  date_gmt: '2010-06-03 16:47:19 -0700'
  content: '[...] Day in, day out… » Camcorder to the Web – HD Video on Ubuntu [...]'
- id: 580
  author: Canon 0797V164 Kata Small Shoulder Bag for GL2 Camcorder | 2Studio.net
  author_email: ''
  author_url: http://2studio.net/5051/canon-0797v164-kata-small-shoulder-bag-for-gl2-camcorder/
  date: '2010-06-03 09:31:06 -0700'
  date_gmt: '2010-06-03 17:31:06 -0700'
  content: '[...] Day in, day out… » Camcorder to the Web – HD Video on Ubuntu [...]'
- id: 665
  author: muthii
  author_email: muthii@muthii.com
  author_url: http://www.muthii.com/blog
  date: '2010-11-18 22:20:03 -0800'
  date_gmt: '2010-11-19 06:20:03 -0800'
  content: "Thanks for showing how you do it, I didn&#039;t know of openshot just
    installed it and am putting together my first project. Thank you for sharing your
    work. \nMy recent post <a href=\"http://muthii.com/blog/?p=329\" rel=\"nofollow\">My
    First 10k run</a> "
---
<p>Problem statement:</p>
<blockquote><p>Grab HD clips from <a href="http://www.camcorderinfo.com/content/Sony-HDR-HC7-Camcorder-Review.htm">Sony HDR-HC7 HDV</a> camcorder and convert them to HD videos on the web (<a href="http://vimeo.com/">Vimeo</a>, <a href="http://youtube.com/">YouTube</a>, etc.) fairly easily on Linux - specifically, <a href="http://ubuntu.com/">Ubuntu</a></p></blockquote>
<p>I've been trying to address this problem for a while now. It has been about a year since I tried last. I remember using <a href="http://www.kinodv.org/">Kino</a> and giving <a href="http://cinelerra.org/">Cinelerra</a> a shot. For variety of reasons, I did not like either and I gave up on the effort.</p>
<p>Recently, when Ubuntu 10.04 shipped with PiTiVi as the default video editor, I decided to give it another go. Since I had used <a href="http://www.openshotvideo.com/">OpenShot</a> briefly in Ubuntu 9.10, I thought it would be educational to try both the video editors to accomplish the task. So I created a short sample video in both these editors - embedded below.</p>
<p>I am a video pro by no means. I am just a novice user trying hard to shoot least shaky HD movies and sharing them with family and friends - while not embarrassing myself! So please take my input and opinions with a grain of salt. But at the end of it all, I think I prefer OpenShot - at least for my camcorder, my level of skill and expertise using video editors.</p>
<p>Now that the result is out of the way, here's the rest of the story...</p>
<h4>Workflow</h4>
<p>Workflow I would like to set up is simple:</p>
<ol>
<li>Grab clips from the camcorder</li>
<li>Convert clips to a format the video editor likes (I would rather not, but necessary with some editors)</li>
<li>Import them into the video editor</li>
<li>Edit/mix the clips and compose the video</li>
<li>Export it to desired target</li>
</ol>
<h4>Grabbing clips from the camcorder</h4>
<p>This is something I learned from my previous experience with Kino. I use <code><a href="http://freshmeat.net/projects/dvgrab/">dvgrab</a></code> to grab clips from the camcorder. Here is the source of the script I use:</p>
<p><script src="http://gist.github.com/421988.js?file=my-dvgrab-script.sh"></script></p>
<p>Sony HDR-HC7 is an <a href="http://en.wikipedia.org/wiki/HDV">HDV</a> camcorder. As such, the above script grabs the clips in form of a sequence of MPEG-2 transport stream (<code>.m2t</code>) files. I use the <code>-timestamp</code> option so that the names of the files include the time when the video was recorded. I also store the output of this script for later use. It includes useful information about the clips - like the timecode, length of the clip in frames, size of the clip etc. Here's a sample output:</p>
<p><script src="http://gist.github.com/421988.js?file=Output+of+the+script"></script></p>
<h4>Using OpenShot</h4>
<h5>Importing video</h5>
<p>One thing I really loved about OpenShot is the fact that it can consume <code>.m2t</code> files! Kino did not, Cinelerra did not, PiTiVi does not. So this is great. It completely eliminates one step in my workflow.</p>
<p>Import function in OpenShot (the big green '+' sign in the toolbar) allows you to add video (my <code>.m2t</code> files), audio and other media files.</p>
<h5>Editing video</h5>
<p>For a simple video, like the one I created for this experiment, all you need to do is drag the clips into the timeline - the lower part of the interface - and position them to define the sequence of scenes in the movie.</p>
<p>Here are some editing/mixing features of OpenShot I used in the making of the sample video:</p>
<ul>
<li>The razor tool can be used to snip clips at any given position</li>
<li>Markers can be added on the timeline to mark significant positions in the timeline</li>
<li>Video in a clip can be turned ON or OFF</li>
<li>Audio in a clip can be turned ON or OFF</li>
<li>Effects like Fade in/Fade out can be applied to individual tracks</li>
<li>There are many transitions and effects, which I did not use in the sample video</li>
</ul>
<p>I did not play with titles, credits or subtitles, so I cannot say much about those features. All in all, you can do some basic editing and mixing really well.</p>
<h5>Exporting video</h5>
<p>Another thing you got to love is that OpenShot comes with canned export profiles. Profiles have export parameters set to work with DVD, Web (Vimeo, Youtube and the likes) etc. The fact that export to Vimeo-HD and Youtube-HD worked so well, make me feel very optimistic about DVD export - which is going to be my next endeavor.</p>
<p>Here's a screenshot of the export dialog.</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/openshot-export-vimeo.png"><img src="http://tech.mahesha.com/wp-content/images/openshot-export-vimeo.png" alt="Exporting for Vimeo using OpenShot - Click for full size" width="525px"></a></p>
<div class="caption">Exporting for Vimeo using OpenShot</div>
</div>
<p>And finally, here are the videos out of OpenShot, on both Vimeo (exported with Vimeo-HD profile) and Youtube (exported with Youtube-HD profile). </p>
<p>OpenShot Vimeo HD video:</p>
<p><object width="549" height="309"><param name="allowfullscreen" value="true" /><param name="allowscriptaccess" value="always" /><param name="movie" value="http://vimeo.com/moogaloop.swf?clip_id=12195545&amp;server=vimeo.com&amp;show_title=1&amp;show_byline=1&amp;show_portrait=0&amp;color=ffffff&amp;fullscreen=1" /><embed src="http://vimeo.com/moogaloop.swf?clip_id=12195545&amp;server=vimeo.com&amp;show_title=1&amp;show_byline=1&amp;show_portrait=0&amp;color=ffffff&amp;fullscreen=1" type="application/x-shockwave-flash" allowfullscreen="true" allowscriptaccess="always" width="549" height="309"></embed></object></p>
<p>OpenShot Youtube HD video:</p>
<p><object width="560" height="340"><param name="movie" value="http://www.youtube.com/v/M_8QtP2AKlM&hl=en_US&fs=1&rel=0&hd=1"></param><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param><embed src="http://www.youtube.com/v/M_8QtP2AKlM&hl=en_US&fs=1&rel=0&hd=1" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" width="560" height="340"></embed></object></p>
<h4>Using PiTiVi</h4>
<h5>Importing video</h5>
<p>Like I mentioned, PiTiVi does not consume <code>.m2t</code> files. Apparently, it has the capability, but <a href="https://bugs.launchpad.net/ubuntu/+source/gstreamer0.10/+bug/574050">there's probably a bug</a> currently, that keeps it from recognizing the files correctly. So there's hope!</p>
<p>But for now, you must convert the <code>.m2t</code> files into a format that PiTiVi can read. I used <code>ffmpeg</code> to do so. Here's the command (and its output) I used for <code>.m2t</code> to <code>.mpg</code> conversion:</p>
<p><script src="http://gist.github.com/421988.js?file=m2t+to+mpg+conversion"></script></p>
<p>Converted <code>.mpg</code> files can now be imported and worked with in PiTiVi.</p>
<h5>Editing video</h5>
<p>Much like OpenShot, PiTiVi allows you to add video, audio and other media files to a project. You then drag the clips in the time line and position them to define the sequence of scenes in the movie.</p>
<p>Here are some editing/mixing features of PiTiVi I used in the making of the sample video:</p>
<ul>
<li>The scissor tool can be used to snip clips at any given position</li>
<li>I could only add one marker (the cursor), but I am sure there is a way to add more. I just did not try to find it</li>
<li>Instead of Fade In/Out effects or completely turning ON or OFF a clip, PiTiVi allows you to set track levels (brightness for video tracks, volume for audio tracks). The levels can vary through the track depending on the levels in the beginning and the end of track. I think this provides an added level of flexibility. But also, at the same time, makes simple Fade In/Out slightly harder to implement. I like it though</li>
<li>Audio from a video track can be separated into an independent track. This, also, I think is a very handy feature</li>
</ul>
<p>Again, I did not play with titles, credits or subtitles, so I cannot say much about those features. I also did not easily find any transitions or effects, that could be applied to tracks.</p>
<p>I had trouble synchronizing audio and video in PiTiVi (synchronizing the 'gong' with dropping of CD sleeve). I was finally able to synchronize the two with a lot of trial-and-error. The one that rendered kind of synchronized (one below) does not actually look synchronized in the preview. The preview in PiTiVi did not seem very accurate.</p>
<h5>Exporting video</h5>
<p>PiTiVi does not come with canned export profiles. Although I found a way to <a href="http://eugenia.gnomefiles.org/images2/pitivi.png">export to Vimeo-HD</a> on the Vimeo help sites. It is left to the users to do the research. As you might notice though, the audio/video out of PiTiVi is a bit choppy at times. I probably did not get all the export parameters right. But then again, PiTiVi does not make it any easier.</p>
<p>Here's the screenshot of the export dialog of PiTiVi:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/pitivi-export-vimeo.png"><img src="http://tech.mahesha.com/wp-content/images/pitivi-export-vimeo.png" alt="Exporting for Vimeo using PiTiVi - Click for full size" width="525px"></a></p>
<div class="caption">Exporting for Vimeo using PiTiVi</div>
</div>
<p>And here is the resulting Video:</p>
<p><object width="560" height="340"><param name="movie" value="http://www.youtube.com/v/9p5gsaFQmb8&hl=en_US&fs=1&rel=0"></param><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param><embed src="http://www.youtube.com/v/9p5gsaFQmb8&hl=en_US&fs=1&rel=0" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" width="560" height="340"></embed></object></p>
<h4>Conclusion</h4>
<p>I tend to compare video editors in three different categories - Import, Editing and Export. A good video editor should support a wide variety of input formats. It should have a good balance of powerful and easy-to-use editing features. It should export video in formats that can be played flawlessly on popular targets like the Web (Youtube, Vimeo, etc.) and media players (DVD/VCD players, desktop media players, etc.).</p>
<p>At the time of this writing, I think OpenShot trumps in all the three categories.</p>
<ul>
<li>In my case, PiTiVi could not import <code>.m2t</code> files. This added a step in my workflow. Hopefully this is temporary and will be fixed soon</li>
<li>PiTiVi has some neat editing features, but lack of transitions and effects shifts the balance in OpenShot's favor. Also everything you can do in PiTiVi can be achieved in OpenShot to some extent.</li>
<li>OpenShot has export profile for popular targets. This is a must for anyone who doesn't want to get lost in the many gory details of conversion parameters and their optimal values - certainly for me</li>
</ul>
<p>Looks like the Linux video editor scene is starting to look up. I hope it only gets better from here. </p>
<p>If something I mentioned in this post is inaccurate/wrong, please point it out in the comments. Hope this helps!</p>
<p><center><br />
[polldaddy poll=3293312]<br />
</center></p>
