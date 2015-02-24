---
layout: post
status: publish
published: true
title: Javascript performance - writing to innerHTML
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 33
wordpress_url: http://tech.mahesha.com/2007/07/05/javascript-performance-writing-to-innerhtml/
date: '2007-07-05 11:33:57 -0700'
date_gmt: '2007-07-05 19:33:57 -0700'
categories: []
tags:
- Javascript
- AJAX
comments:
- id: 563
  author: egor4eg
  author_email: noemail@intensedebate.com
  author_url: ''
  date: '2010-04-07 13:46:37 -0700'
  date_gmt: '2010-04-07 13:46:37 -0700'
  content: "create array and create string using array.push() method. It is much quicker
    than += string concatenation in IE6 and IE7. So, use something like: var html_str
    = new Arrray(); html_str.push(&quot; \n&lt;LI class=&quot;); \nhtml_str.push(it_li_class);
    \n \nthis.port.innerHTML = html_str; \n....... \nhtml_str.push(&quot; a &lt;&gt;&quot;);</li> "
- id: 564
  author: Mahesh Asolkar
  author_email: mahesh@mahesha.com
  author_url: http://intensedebate.com/people/asolkar
  date: '2010-04-07 16:52:21 -0700'
  date_gmt: '2010-04-07 16:52:21 -0700'
  content: "egor4eg, thanks for the input. I&#039;ll sure try it out. \n \nI wrote
    the AJAX experiment a while back, when I was unaware of jQuery. If I rewrite it,
    I&#039;d probably use jQuery. jQuery has made my recent work very fast to implement,
    efficient in execution, easily compatible across most browsers. \n \nBut the experiments
    without jQuery were educational, and necessary to appreciate the value of libraries
    like jQuery! \nMy recent post <a href=\"http:\\/\\/github.com\\/asolkar\\/emptyem\\/commit\\/818fc2cc52a88d690b831cbea1d33a1c27e17252\"
    target=\"_blank\">Updated preferences screenshot</a> "
---
<p>Recently I was investigating why the performance of <a href="http://st.mahesha.com/deals/" title="AJAX Experiment - Big Deal">one of my AJAX experiment</a> is so bad.</p>
<p>This page uses a Perl CGI script to query a handful of <em>deals</em> sites for syndication of their deals and puts them together in one big RSS. Then the Javascript part displays the big collection of deals as a list. The list can be then narrowed down based on keywords as they are typed.</p>
<p>Since the big RSS usually contains more than 300 entries, the Javascript that was converting the entries into list items in an unordered list, was taking upto 10-15 seconds to render. This was not very pleasant.</p>
<p>Here's how that part of the code looked:</p>
<pre>
  for ( it = 0; it < items.length; it++) {
    var item = items[it];
    var it_title = item.getElementsByTagName('title').item(0).firstChild.data;
    var it_link  = item.getElementsByTagName('link').item(0).firstChild.data;

    <b>this.port.innerHTML += "&lt;li class=" + it_li_class + "&gt;&lt;a href=\"" 
                           + it_link + "\" target=\"feedr_win\"&gt;"
                           + it_title + "&lt;/a&gt;";</b>
  }
</pre>
<p>After a few experiments, I found that the assignment to <code>this.port.innerHTML</code> was the one that was most expensive. I modified the code to read:</p>
<pre>
  <b>var html_str = "";</b>

  for ( it = 0; it < items.length; it++) {
    var item = items[it];
    var it_title = item.getElementsByTagName('title').item(0).firstChild.data;
    var it_link  = item.getElementsByTagName('link').item(0).firstChild.data;

    <b>html_str += "&lt;li class=" + it_li_class + "&gt;&lt;a href=\"" 
             + it_link + "\" target=\"feedr_win\"&gt;"
             + it_title + "&lt;/a&gt;";</b>
  }
  
  <b>this.port.innerHTML = html_str;</b>
</pre>
<p>That cut the time to less than a second. More than a 10x-15x performance improvement.</p>
<p>Next time I write something directly into <code>innerHTML</code> from Javascript in a loop, I am going to try and see if I can collect the text first and then write it into <code>innerHTML</code>.</p>
