---
layout: post
status: publish
published: true
title: Building Alpine on Hardy Heron
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 114
wordpress_url: http://tech.mahesha.com/?p=114
date: '2008-08-24 15:37:54 -0700'
date_gmt: '2008-08-24 23:37:54 -0700'
categories:
- Uncategorized
tags:
- Ubuntu
- Hardy Heron
- Alpine
comments:
- id: 93
  author: Soma Bulusu
  author_email: bsoma@hotmail.com
  author_url: ''
  date: '2009-03-26 09:22:44 -0700'
  date_gmt: '2009-03-26 17:22:44 -0700'
  content: "Hi,\r\n\r\nI was wondering how you got it to work with Exchange. I was
    able to get it configured for GMAIL, but how are you using it with exchange? If
    possible, can you send me the .pinerc file without your sensitive information
    to my mail address?\r\n\r\nThanks,\r\nSoma"
- id: 94
  author: Mahesh Asolkar
  author_email: mahesh@mahesha.com
  author_url: http://tech.mahesha.com
  date: '2009-03-26 13:32:35 -0700'
  date_gmt: '2009-03-26 21:32:35 -0700'
  content: |-
    To work with Exchange, these settings in .pinerc, I think, are important:

    <code>
    inbox-path={SERVER/tls/novalidate-cert/user=USER}inbox
    folder-collections="My Exchange Folders" {SERVER}Inbox/[*]
    </code>

    I also have these, to map 'Sent Items', 'Deleted Items' and 'Drafts' folders:

    <code>
    default-fcc={SERVER/tls/novalidate-cert/user=USER}Sent Items
    trash-folder={SERVER/tls/novalidate-cert/user=USER}Deleted Items
    postponed-folder={SERVER/tls/novalidate-cert/user=USER}Drafts
    </code>

    In all the above, replace <code>SERVER</code> with your exchange server and <code>USER</code> with your username. Use the same server you use in Outlook (or your existing client). You can also get the server name from the Outlook Web Access under the <em>Options-&gt;About</em> section. It is called 'Outlook Web Access host name'.

    Let me know if that works for you.
- id: 640
  author: aleka
  author_email: arpaxtra@gmail.com
  author_url: ''
  date: '2010-09-08 11:47:11 -0700'
  date_gmt: '2010-09-08 19:47:11 -0700'
  content: 'the instructions still work with Ubuntu 10.4 (Lucid Lynx), thanks! '
---
<p>Lately, I have developed a liking for the <a href="http://www.washington.edu/alpine/" title="Alpine website">Alpine Messaging System</a>. It is a text based email client that runs on a variety of platforms. I use it with Gmail IMAP at home and MS Exchange at work. In both cases, it works beautifully.</p>
<p>Pre-compiled binaries for a good number of platforms are available on the <a href="http://www.washington.edu/alpine/acquire/" title="Acquire Alpine">apline website</a>. But if you are not in a position to use the pre-compiled binaries - say because you do not have root privileges, or binary is not available for your platform, or may be you just<br />
want to use the bleeding edge development code - you can build the alpine application from source. The following steps are specific to building the latest SVN snapshot on Ubuntu Hardy Heron. It may/may not work on other OSes.</p>
<p><b>Prepare your system</b></p>
<p>Get all the (known) prerequisites. From my experience, these are required:</p>
<ul>
<li>libncurses5-dev to get rid of the following error:</li>
</ul>
<blockquote><p><code>configure: error: Terminfo/termcap not found</code></p></blockquote>
<ul>
<li>libpam0g-dev and libssl-dev to get rid of some SSL related errors.</li>
</ul>
<p>To get the above use the following in terminal:</p>
<pre>
  % sudo apt-get install subversion libncurses5-dev \
                         libpam0g-dev libssl-dev
</pre>
<p><b>Get the source code</b></p>
<p>Get the latest source snapshot. Following few steps are one time. After the initial snapshot is acquired with svn checkout, svn update can be used to update the source snapshot:</p>
<pre>
  % mkdir ..../alpine
  % cd ..../alpine
  % svn checkout \
        https://svn.cac.washington.edu/public/alpine/snapshots/
</pre>
<p>Accept the certificate (permanently) if required.</p>
<p><b>Configure, compile and install</b></p>
<p>Now use the familiar <i>configure, make, make install</i> routine to build and install Alpine.</p>
<pre>
  % cd .../alpine/snapshots
  % svn update
  % ./configure --prefix=/opt/apps/alpine
                --with-local-password-cache-method
  % make
  % sudo make install
</pre>
<p>I was overly optimistic in using <code>--with-local-password-cache-method</code>. I was hoping that Alpine would store my account passwords in Gnome Keyring! It did not work quite like that. I need to enter my email passwords every time I start Alpine.</p>
<p>Other way to automate password entry is to use the <code>--with-passfile</code> configure option. But it is known to be unsafe.</p>
<p>Happy messaging!</p>
<p>EDIT: Trying to recompile alpine on Intrepid, I discovered that <code>libssl-dev</code> is also required.</p>
