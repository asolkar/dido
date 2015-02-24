---
layout: post
status: publish
published: true
title: Gmail IMAP disappointing :(
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 76
wordpress_url: http://tech.mahesha.com/2007/10/24/gmail-imap-disappointing/
date: '2007-10-24 19:55:18 -0700'
date_gmt: '2007-10-25 03:55:18 -0700'
categories:
- Uncategorized
tags:
- Google
- Gmail
- IMAP
comments:
- id: 38
  author: Gmail IMAP - getting used to
  author_email: ''
  author_url: http://tech.mahesha.com/2007/11/07/gmail-imap-getting-used-to/
  date: '2007-11-07 00:01:16 -0800'
  date_gmt: '2007-11-07 08:01:16 -0800'
  content: '[...]     Gmail IMAP disappointing :(   Nov [...]'
---
<p><a href="http://gmailblog.blogspot.com/2007/10/sync-your-inbox-across-devices-with.html" title="Sync your inbox across devices with free IMAP">I noticed today</a> that Google has started rolling out <a href="https://mail.google.com/support/bin/answer.py?answer=75725&topic=12762" title="Gmail IMAP help">support for IMAP on Gmail accounts</a>. This is something I was waiting for <a href="http://tech.mahesha.com/2007/07/30/the-never-ending-google-wishlist/" title="My Google wishlist">since a long time</a>. Gmail's POP access is too inadequate when it came to accessing Gmail from multiple desktop email clients.</p>
<p>I was lucky enough to have one of my accounts enabled for IMAP. First thing I did was start playing around with it.</p>
<p>My first impression - I hope I grow out if it - is that Google's mapping of Gmail features to IMAP features is very disappointing. It's workable, but may be I was expecting something smarter from folks at Google. After using Gmail IMAP for a few hours, I've started to think that the POP option suits me better for access with desktop email clients (whooda thunk!). Web Gmail is still my favorite flavor - but it does not make messages available for off-line use (Say what? <a href="http://gears.google.com/" title="Google Gears Beta">Gears</a>?).</p>
<p>So what is it that I don't like about the new IMAP access?</p>
<ul>
<li>I like the concepts of <em>labels</em> or <em>tags</em> when it comes to organizing files, email messages, things - as against folders. Tags are much easier to search, manage. If a message belongs in two different categories, you can add two (or more) tags. You don't have to waste time deciding which folder to file it in. Labels and Folders are two completely orthogonal concepts - they can coexist, but they cannot be mapped. I was hoping that Google kept them that way. As it turns out, Google has tried to map Labels to folders. As one would expect, this causes <a href="http://mail.google.com/support/bin/answer.py?answer=78760&topic=12762" title="Why aren't my messages threaded?">multiple copies of messages</a> on the desktop.</li>
<li>It may be just my lack of knowledge about IMAP, but I had thought that information about <em>labels</em>, <em>stars</em> etc. would be carried in custom message headers, so that desktop applications can use the labels as they are on Gmail web. There would just be one big <em>All Mail</em> folder</li>
<li>From what I have read though, there are a lot of Gmail users who hate (or don't understand) labels and dearly miss the concept of folders. Rejoice suckers!</li>
<li>I configured Thunderbird 3.0 (pre-release) and Apple Mail to use IMAP access to Gmail. Things look pretty OK on Thunderbird. Notice this, all Gmail folders are created under an account tree (account name obscured).
<div class="img_container">
<img src="/wp-content/images/imap-gmail-tbd-gutsy.png" alt="Gmail IMAP folders on Thunderbird on Ubuntu Gutsy">
<div class="caption">Gmail IMAP folders on<br>Thunderbird on Ubuntu Gutsy</div>
</div>
<p>On Apple Mail though, Gmail folders are created at the top level.</p>
<div class="img_container">
<img src="/wp-content/images/imap-gmail-apple-mail.png" alt="Gmail IMAP folders on Apple Mail">
<div class="caption">Gmail IMAP folders on Apple Mail</div>
</div>
<p>If one wants to configure multiple Gmail accounts, I can see it work in Thunderbird with the [Gmail] folders under each account tree. On Apple Mail will the [Gmail] for different accounts stomp on each other? I am not even going to try that before I hear from someone else who has done that without problems.</p>
</li>
<li>This label-folder mapping also causes <a href="http://mail.google.com/support/bin/answer.py?answer=78757&topic=12762" title="What are these new labels in my web Gmail?">funky things</a> to happen to Web Gmail when you move messages on the desktop client. Not something I found very impressive.</li>
</ul>
<p>So there... Like I said, I hope this changes, but for now, I am not a big fan of Gmail IMAP.</p>
