---
layout: post
status: publish
published: true
title: Gmail IMAP - getting used to
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 77
wordpress_url: http://tech.mahesha.com/2007/11/07/gmail-imap-getting-used-to/
date: '2007-11-07 00:01:10 -0800'
date_gmt: '2007-11-07 08:01:10 -0800'
categories:
- Uncategorized
tags:
- Google
- Gmail
- IMAP
comments: []
---
<p>Looks like I am growing out of the <a href="http://tech.mahesha.com/2007/10/24/gmail-imap-disappointing/" title="Gmail IMAP disappointing :(">initial disappointment</a> with Gmail IMAP. Although the mapping of <em>labels</em> to <em>folders</em> is still uncomfortable, thanks to some useful tips floating around on the web, I have been able to configure my clients much better now.</p>
<p>I did not have a lot of trouble with Thunderbird to begin with. I use the nightly build on Linux, it works fine with Gmail IMAP. After mapping <em>Trash</em>, <em>Drafts</em>, <em>Sent</em> and <em>Spam</em> folders to those on <em>[Gmail]</em>, things work great. The only flaw I see is that even after mapping Thunderbird's <em>Trash</em> folder to <em>[Gmail]/Trash</em>, Thunderbird's Trash folder stays put. This causes the unwelcome <em>[Imap]/Trash</em> label on the web interface.</p>
<div class="img_container">
<img src="/wp-content/images/imap-gmail-tbd-gutsy-trashes.png" alt="Two Trash folders on Thunderbird on Ubuntu Gutsy"></p>
<div class="caption">Two Trash folders on<br />Thunderbird on Ubuntu Gutsy</div>
</div>
<p>On the Mac, I had expressed my doubts on how Mail.app would handle multiple IMAP accounts. This was because when I configured one Gmail IMAP account, Gmail folders were created at the top level. I was worried that more than one accounts would step on each other's folders. Thankfully, Mail.app handles multiple accounts just fine. Mapping Mail.app's <em>Trash</em>, <em>Drafts</em>, <em>Sent</em> and <em>Spam</em> folders to Gmail's is easy. Select <em>[Gmail]/Trash</em>, for example, and use <em>Mailbox -> Use This Mailbox For -> Trash</em> from the menu-bar. Repeat that for other special folders.</p>
<p>So, there are some rough edges as far as the clients' implementation of IMAP goes, Gmail labels are rendered pretty much useless - but all the clients are in sync! Not bad at all...</p>
