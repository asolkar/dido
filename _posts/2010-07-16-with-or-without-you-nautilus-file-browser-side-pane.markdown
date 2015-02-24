---
layout: post
status: publish
published: true
title: With or Without You - Nautilus File Browser Side Pane
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 421
wordpress_url: http://tech.mahesha.com/?p=421
date: '2010-07-16 16:19:17 -0700'
date_gmt: '2010-07-17 00:19:17 -0700'
categories:
- Uncategorized
tags:
- Linux
- Gnome
- Nautilus
comments: []
---
<p>If you are a <a href="http://www.gnome.org/">Gnome Desktop</a> user on Linux and use <a href="http://live.gnome.org/Nautilus">Nautilus File Manager</a> to browse your files, here's a handy tip.</p>
<p>When you access your files via the <em>Places</em> menu, (e.g., <em>Places &rarr; Home Folder</em>), there are two ways you can view your files (among many other ways, I guess):</p>
<ul>
<li>The file manager window has a browser pane on the left. This pane (also called the <em>Side Pane</em>) provides easy access to your bookmarks, mounted drives, etc. This is my preferred way. Here's what it looks like:
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/folders-with-browser.png"><img src="http://tech.mahesha.com/wp-content/images/folders-with-browser.png" alt="File manager with browser pane - Click for full size"></a></p>
<div class="caption">File manager with browser pane</div>
</div>
</li>
<li>The file manager window does not have a browser pane. One of the reasons I am not so comfortable with this is that it opens a new window when you double-click on a folder. Too many windows can result if you are browsing around. And here's how it looks:
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/folders-without-browser.png"><img src="http://tech.mahesha.com/wp-content/images/folders-without-browser.png" alt="File manager without browser pane - Click for full size"></a></p>
<div class="caption">File manager without browser pane</div>
</div>
</li>
</ul>
<p>It is a matter of personal preference. Since I use Ubuntu extensively, and its default is to show the file manager with the side pane, I am kind of used to it. So when I started working on another computer where the default was without the side pane, I wasn't very comfortable.</p>
<p>But as it turns out, like with many other customization options on Linux, this was easy to change.</p>
<p>All it takes is to set the configuration key <code>/apps/nautilus/preferences/always_use_browser</code> to be <code>true</code>. There are a couple of ways you can do that.</p>
<p><b>With the Configuration Editor GUI</b></p>
<p>You can start the Configuration Editor from the <em>Application &rarr; System Tools</em> menu. Or use the <code>gconf-editor</code> command in the Terminal. Once in the Configuration Editor, navigate to the <code>/apps/nautilus/preferences/always_use_browser</code> key in the left side pane:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/gconf-nautilus-always_use_browser.png"><img src="http://tech.mahesha.com/wp-content/images/gconf-nautilus-always_use_browser.png" alt="/apps/nautilus/preferences/always_use_browser key in the Configuration Editor - Click for full size" width="525px"></a></p>
<div class="caption"><code>/apps/nautilus/preferences/always_use_browser</code> key in the Configuration Editor</div>
</div>
<p>Check the checkbox to enable the preference.</p>
<p><b>With <code>gconftool-2</code> command</b></p>
<p>Much easier way, for folks who are not so much against the Terminal. Open the Terminal and use this command:</p>
<pre>
gconftool-2 --set --type=bool /apps/nautilus/preferences/always_use_browser true
</pre>
<p>So there. And while we are at it, a quick poll, may be?</p>
<p><center><br />
[polldaddy poll=3481100]<br />
</center></p>
