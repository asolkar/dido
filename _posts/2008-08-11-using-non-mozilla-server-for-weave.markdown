---
layout: post
status: publish
published: true
title: Using non-Mozilla server for Weave
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 89
wordpress_url: http://tech.mahesha.com/?p=89
date: '2008-08-11 15:40:38 -0700'
date_gmt: '2008-08-11 23:40:38 -0700'
categories:
- Uncategorized
tags:
- Mozilla
- Weave
comments:
- id: 60
  author: Synchronize notes with Tomboy
  author_email: ''
  author_url: http://tech.mahesha.com/2008/08/23/synchronize-notes-with-tomboy/
  date: '2008-08-23 13:29:46 -0700'
  date_gmt: '2008-08-23 21:29:46 -0700'
  content: '[...]     Using non-Mozilla server for Weave   Aug [...]'
---
<p>If you use <a href="http://labs.mozilla.com/projects/weave/" title="Weave home page">Weave</a>, you've probably noticed that Mozilla servers are currently overloaded. Accounts are not working. My account authenticates (If I access
<pre>https://services.mozilla.com/user/&lt;user_name&gt;/</pre>
<p> it asks for and accepts my credentials), but I get a "Not Found" 404 error. The accounts that do work, are very slow.</p>
<p>Like always, I went forumming, trying to get to the bottom of this trouble. I came across some helpful posts at the <a href="https://labs.mozilla.com/forum/index.php/board,19.0.html" title="Weave Forum">Weave forums</a>. Posts from <a href="https://labs.mozilla.com/forum/index.php?topic=1482.msg6495#msg6495">covidium</a> and <a href="https://labs.mozilla.com/forum/index.php?topic=1482.msg6502#msg6502">netoak</a> are especially useful. This post is just a compilation of steps I followed to get my Weave working again.</p>
<p><strong>Get a WebDAV host</strong><br />
I guess there are only a handful of these, that are free. I tried to find one in the US, but couldn't. I just used the one that <a href="https://labs.mozilla.com/forum/index.php?topic=1482.msg6502#msg6495">covidium</a> suggested. I opened a free account at <a href="http://www.mydisk.se/" title="myDisk">myDisk.se</a>.</p>
<p><strong>Create directory structure</strong><br />
Weave expects the files to be in a specific directory structure. If you have <code>myserver.com</code> as your server, it will look for
<pre>myserver.com/user/user_name</pre>
<p> To cater to this, I created a directory called <code>user</code>, then inside it, I created one called <code>user_name</code>.</p>
<p>In retrospect, I should have instead made
<pre>weave/user/user_name</pre>
<p> directory structure. That would keep everything <em>Weave</em> together.</p>
<p><strong>Set Weave's Server Settings</strong><br />
Open Weave's Server Settings (<em>Tools -> Weave -> Preferences...</em>) and then go to the <em>Advanced</em> tab. Replace the default <em>Server Location</em> with
<pre>https://mydisk.se/user_name/</pre>
<p> mydisk makes my files available at <code>https://mydisk.se/user_name/</code>, other hosts may use some other path.</p>
<p>If I had used
<pre>weave/user/user_name</pre>
<p> directory structure, I would set the <em>Server Location</em> to
<pre>https://mydisk.se/user_name/weave/</pre>
<p><strong>Try Weave again</strong><br />
In Weave preferences' <em>Advanced</em> tab, click on the <em>Advanced...</em> button. Click on <em>Reset Login </em>and <em>Reset Server Lock</em> buttons. I did not think it would be required, but I had to quit Firefox and restart it.</p>
<p>Now, sign in to Weave again (<em>Tools -> Weave -> Sign In</em>). Follow the setup wizard as if you are opening a new account. Use username and password from your WebDAV server. Pick a strong passphrase.</p>
<p>At this point, you should be all set.</p>
<p>Do leave feedback to point out errors in the above process, so other readers can benefit too.</p>
<p>My current web host does not provide WebDAV. From what I read, <a href="http://www.dreamhost.com/hosting-features.html#webdav">DreamHost does</a>. I wonder if Weave users who have DreamHost accounts already host their own Weave servers. </p>
