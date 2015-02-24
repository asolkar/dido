---
layout: post
status: publish
published: true
title: 'Pet peeve: font-family'
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 27
wordpress_url: http://tech.mahesha.com/2007/05/11/pet-peeve-font-family/
date: '2007-05-11 09:49:51 -0700'
date_gmt: '2007-05-11 17:49:51 -0700'
categories: []
tags:
- pet peeve
- web
comments: []
---
<p>How many times have you noticed that a web page displays with <a href="http://www.answers.com/topic/serif#Computer_Encyclopedia" title="Sans-Serif fonts">Sans-Serif</a> fonts on Windows or Mac and <a href="http://www.answers.com/topic/serif-1#Computer_Encyclopedia" title="Serif fonts">Serif</a> fonts on Linux?</p>
<p>I see this <a href="http://dailytech.com/" title="Exhibit 1">more</a> <a href="http://quality.mozilla.org/" title="Exhibit 2">often</a> than I would like - and it bugs me. If you view the stylesheets of such websites, in most cases this is due to the improper use of fonts like <em><a href="http://www.answers.com/verdana" title="Verdana font">Verdana</a></em>, <em><a href="http://www.answers.com/topic/helvetica-1#Wikipedia" title="Helvetica font">Helvetica</a></em> and the likes, that may not be available in a normal Linux installation.</p>
<p>The complete definition of <code>font-family</code> style in <a href="http://www.answers.com/main/ntquery?s=CSS" title="Cascading Style Sheets">CSS</a> is as follows: </p>
<pre>
font-family: [[family-name|generic-family]
             [,family-name|generic-family]*] | inherit
</pre>
<p>The solution is that, whenever a font family is specified, its generic version must follow. For example:</p>
<pre>
body { font-family: "Gill Sans Extrabold", Helvetica, sans-serif }
.receipt { font-family: Courier, "Lucida Console", monospace }
</pre>
<p>This will make sure that all browsers display the intended - or at least the closest to the intended - fonts.</p>
<p>There's a neat example at <a href="http://developer.mozilla.org/samples/cssref/font-family.html" title="Proper font-family specification">Mozilla Developer Center</a>.</p>
<p>With the number of Linux users increasing, <a href="http://www.answers.com/QA" title="Quality Assurance">QA</a> folks should consider testing their websites on Linux too.</p>
