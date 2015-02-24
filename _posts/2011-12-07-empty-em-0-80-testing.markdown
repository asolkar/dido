---
layout: post
status: publish
published: true
title: Empty 'em 0.80 testing
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 545
wordpress_url: http://tech.mahesha.com/?p=545
date: '2011-12-07 13:31:20 -0800'
date_gmt: '2011-12-07 21:31:20 -0800'
categories:
- Uncategorized
tags:
- addon
- thunderbird
- emptyem
comments: []
---
<p>I am seeking testing and feedback on a new version of Empty' em. There are some implementation changes that I would like to test on multiple platforms and different versions of Thunderbird before submitting on AMO. Following is the summary of changes:</p>
<ul>
<li>Moved to using <a href="https://developer.mozilla.org/en/Extensions/Inline_Options" title="Inline Options" target="_blank">Inline Options</a>. This requires version 7.* or greater. On older versions, old preferences should work</li>
<li>Added a preference to disable the notification that appears after all configured folders have been emptied</li>
<li>Optimization change: Remove the folder listener that was added to track folders being emptied. No functional change, just makes the add-on a good citizen by not consuming resources when it is not active</li>
</ul>
<p>You can provide feedback at:</p>
<blockquote><p>  <a href="https://docs.google.com/spreadsheet/viewform?formkey=dDJpRFc1MUFuQzJDckhnUnlpdUUxUGc6MQ" title="Empty 'em 0.80 testing Google Docs form" target="_blank">Empty 'em 0.80 testing Google Docs form</a>
</p></blockquote>
<p>Here's what the inline options look like:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/emptyem-inline-options.png"><img width="500px" alt="Empty 'em Inline Options - Click for full size" src="http://tech.mahesha.com/wp-content/images/emptyem-inline-options.png"/></a>
<p/>
<div class="caption">Empty 'em Inline Options – Click for full size</div>
</div>
<p>Cheers!</p>
