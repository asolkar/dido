---
layout: post
status: publish
published: true
title: Synchronize notes with Tomboy
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 101
wordpress_url: http://tech.mahesha.com/?p=101
date: '2008-08-23 13:29:36 -0700'
date_gmt: '2008-08-23 21:29:36 -0700'
categories:
- Uncategorized
tags:
- Tomboy
- WebDAV
comments:
- id: 62
  author: Sandy
  author_email: sanfordarmstrong@gmail.com
  author_url: http://automorphic.blogspot.com
  date: '2008-08-23 17:27:45 -0700'
  date_gmt: '2008-08-24 01:27:45 -0700'
  content: 'Thanks for reminding me about that patch...need to get that reviewed/committed!  If
    you run into any issues with sync, please file bugs.  I hope to fix sync bugs
    #535279 and #522424 next week during hack week (also, I plan to make Tomboy fairly
    functional on Windows and Mac OS X, but I can''t promise that sync will work).'
- id: 63
  author: Mahesh
  author_email: mahesh@mahesha.com
  author_url: http://tech.mahesha.com
  date: '2008-08-24 09:30:50 -0700'
  date_gmt: '2008-08-24 17:30:50 -0700'
  content: Glad to hear about Windows and Mac OS X ports! I'll love to be an early
    adopter and file some bugs - hopefully help get sync to work.
---
<p>I have been using <a href="http://www.gnome.org/projects/tomboy/index.html" title="Simple note-taking. Powerful ideas">Tomboy Notes</a> on my Linux machines for more than a couple of years now. Needless to say, I often wished that notes on the other computer were also accessible to be on the one I am working on, at that moment. I was aware that it has a <a href="http://live.gnome.org/Tomboy/PluginList" title="Tomboy WebDAV sync via plugin">Synchronization option - using WebDAV</a>. But, a few times I tried it, I was not successful at getting that to work.</p>
<p>Few days back, I had some success <a href="http://tech.mahesha.com/2008/08/11/using-non-mozilla-server-for-weave/" title="Using non-Mozilla server for Weave">using non-Mozilla server with Weave</a>. In the process, I got a WebDAV account at mydisk.se. Now that I had a WebDAV account, I thought I'd give Tomboy Synchronization another shot.</p>
<p>I built Tomboy from the latest svn source. This was easy, thanks to very <a href="http://live.gnome.org/Tomboy/Developers" title="Tomboy build instructions">clear instructions on the Tomboy Wiki</a>.</p>
<pre>
  % cd /my/source/directory
  % svn co http://svn.gnome.org/svn/tomboy/trunk tomboy
  % cd tomboy
  % ./autogen.sh --prefix=/opt/apps/tomboy \
                 --disable-scrollkeeper
  % make
  % make install
</pre>
<p>On the first synchronization attempt, I got an error indicating that fuse/wdfs was not installed. To fulfill this dependency, I did the following:</p>
<pre>
  % cd /my/source/directory
  % wget http://noedler.de/projekte/wdfs/wdfs-1.4.2.tar.gz
  % tar xzvf wdfs-1.4.2.tar.gz
  % cd wdfs-1.4.2
  % ./configure
  % make
  % sudo make install
</pre>
<p>To get wdfs installed, I had to install the glib2.0 development modules:</p>
<pre>
  % sudo apt-get install libgtk2.0-dev
</pre>
<p>With this, I was all set for the first sync. However, due to a <a href="http://bugzilla.gnome.org/show_bug.cgi?id=499841" title="Bug 499841 – tomboy problems communicating with gnome keyring">bug</a>, that was not quite possible. But since I had the source, and bug report has the fix, I tried it out. I built Tomboy again, with the suggested fix. It worked! I have that build available in the <a href="http://tech.mahesha.com/downloads/" title="Downloads">downloads section</a> for trying out.</p>
<p>A little work, and now my Linux machines have access to all my notes and stickies! I haven't found a Mac app that has WebDAV synchronization of notes. If there is one, I'd love to try it out. The <a href="http://en.wikipedia.org/wiki/Stickies" title="Stickies">stickies utility in Mac OS X</a> could really use some synchronization feature - not via <em>.me</em>.</p>
<p>I use <a href="http://www.google.com/notebook/" title="Google Notebook">Google Notebook</a> a lot too. So some of the <a href="http://live.gnome.org/Tomboy/PluginList" title="New plugin ideas a the bottom of page">Ideas for new plugins</a> sound interesting!</p>
