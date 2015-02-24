---
layout: post
status: publish
published: true
title: Flash 10 on Windows XP - Insufficient disk space!?
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 143
wordpress_url: http://tech.mahesha.com/?p=143
date: '2008-11-22 17:30:34 -0800'
date_gmt: '2008-11-23 01:30:34 -0800'
categories:
- Uncategorized
tags:
- Flash
- Windows XP
comments:
- id: 70
  author: Jon
  author_email: jonmarfleet@yahoo.com
  author_url: ''
  date: '2008-12-11 07:40:57 -0800'
  date_gmt: '2008-12-11 15:40:57 -0800'
  content: "I have the same problem as mentioned however the subst command didn't
    work for me. For some reason when i upgraded my computer it has assigned J:/ as
    my primary drive.  \r\n\r\nIm trying to install flash player but every time i
    try and install it pops up saying insufficient disk space? (Im guessing thats
    because its trying to find my C:/....which has nothing on it) How do i change
    this?\r\n\r\nive tried changing the drive letters but it wont let me do that either!
    HELP!!!  \r\n\r\nthanks\r\nJon"
- id: 72
  author: Mahesh Asolkar
  author_email: mahesh@mahesha.com
  author_url: http://tech.mahesha.com
  date: '2008-12-11 14:10:09 -0800'
  date_gmt: '2008-12-11 22:10:09 -0800'
  content: 'Jon, you say your primary drive is ''J:/'', but you did use ''subst C:
    J:\'' (back-slash, not a forward-slash), correct?'
- id: 75
  author: Kim
  author_email: kwhite@cvalley.net
  author_url: ''
  date: '2009-01-13 19:25:18 -0800'
  date_gmt: '2009-01-14 03:25:18 -0800'
  content: 'omg thank you SOOOO much. I''ve been pulling my hair out. When we reloaded
    the computer, had the printer hooked up and it grabbed C: first so the HD is F:.
    I thought I was going to go nuts!! This worked like a charm!!!! You are a GENIUS!!!'
- id: 76
  author: Antony
  author_email: philipdru@ntlworld.com
  author_url: ''
  date: '2009-01-23 15:12:32 -0800'
  date_gmt: '2009-01-23 23:12:32 -0800'
  content: Same problem with Adobe Flash on XP Pro, but when I try substituting primary
    drive letter I get 'Drive already SUBSTed'. I have a second internal HDD as well
    as an external HDD, which may have something to do with it I don't know. I can
    alter all drive letters except the one assigned arbitrarily at installation. Any
    advice appreciated.
- id: 77
  author: Antony
  author_email: philipdru@ntlworld.com
  author_url: ''
  date: '2009-01-23 15:26:53 -0800'
  date_gmt: '2009-01-23 23:26:53 -0800'
  content: Update - it worked. I don't know what threw me about the message 'Drive
    already SUBSTed' but threw me it did and I forgot to try the installer again.
    If I had a brain I'd be dangerous... Many thanks.
- id: 79
  author: hung
  author_email: hung_ho@yahoo.com
  author_url: ''
  date: '2009-01-28 15:44:59 -0800'
  date_gmt: '2009-01-28 23:44:59 -0800'
  content: "subst is not working for me\r\nget the invalid parameter - c all the time
    i try"
- id: 84
  author: Sarah
  author_email: sarahfoster19@gmail.com
  author_url: ''
  date: '2009-02-08 12:44:12 -0800'
  date_gmt: '2009-02-08 20:44:12 -0800'
  content: "I'm having this same problem with trying to download flash player to firefox.
    What should be my C: drive is actually labeled as H: and although I tried your
    simple fix using the command prompt...it comes up with the following message to
    me: invalid parameter - C:\r\n\r\nnot sure what to do at this point. I also have
    internet explorer which has successfully downloaded flash player, however I do
    not like using that for internet access, and therefore need to get flash player
    to download for firefox still.\r\n\r\nHelp!!!!"
- id: 86
  author: Kyle
  author_email: quile.jones@gmail.com
  author_url: ''
  date: '2009-02-12 14:09:46 -0800'
  date_gmt: '2009-02-12 22:09:46 -0800'
  content: "Hung and Sarah,\r\n\r\nI received the same error because one of my removable
    drives was already labeled C:, and it needed to be changed before the subst command
    would work.\r\n\r\nYou can find the instructions for changing a drive letter here:
    http://support.microsoft.com/kb/307844\r\n\r\nI changed mine to H: temporarily
    and was able to use the original instructions to install Flash Player, no problems."
- id: 87
  author: rye
  author_email: rye@booze.net
  author_url: ''
  date: '2009-02-14 05:46:58 -0800'
  date_gmt: '2009-02-14 13:46:58 -0800'
  content: worked a treat thanks
- id: 89
  author: Deb
  author_email: katesmom99@cox.net
  author_url: ''
  date: '2009-02-20 11:10:01 -0800'
  date_gmt: '2009-02-20 19:10:01 -0800'
  content: I was caught by the same gotcha! Thanks for the easy solution.
- id: 565
  author: Keith Heiner
  author_email: noemail@intensedebate.com
  author_url: ''
  date: '2010-04-12 00:15:06 -0700'
  date_gmt: '2010-04-12 00:15:06 -0700'
  content: 'I already have a C: drive, and wanted to install it on my D: drive.  So
    I tried to subst the C to H and the D to C.  THe first worked, but the second
    said invalid parameter C.  Now, I have an exact copy of the C: drive, and I don&#039;t
    know how to get rid of it.  Please Help. '
---
<p>Its been a while since I booted into Windows XP on my desktop. Today I did. Since Adobe Flash Player 10 is out, I decided to upgrade the existing flash installation - In fact, my bank's website won't work without the upgrade. I downloaded the installer and started it, only to get an error:</p>
<blockquote><p>
You do not have sufficient disk space to complete this installation. Please free 5000 KB and try again.
</p></blockquote>
<p>My disk is nowhere close to being full. A little Googling pointed at <a href="http://kb.adobe.com/selfservice/viewContent.do?externalId=kb406903&sliceId=1" title="Error: "You do not have sufficient disk space to complete this installation" when installing Flash Player 10 on Windows">a known bug in the installer</a> - Apparently, the installer has <code>C:\</code> hard coded in its installation path. So if your boot/system drive is not <code>C:\</code>, the installer dies with a very misleading message, quoted above.</p>
<p>I tried to follow the workaround suggested for Windows XP, but it did not quite work, since <a href="http://support.microsoft.com/kb/307844" title="As per Microsoft Knowledge Base">Changing the drive letter of the system volume or the boot volume is not a built-in feature of the Disk Management snap-in</a>.</p>
<p>Further Googling pointed at a very simple solution. All you need to do is map <code>C:</code> to an existing folder (<code>G:\</code> in my case). So I opened the Command Prompt, and executed the following command:</p>
<pre><a href="http://www.ss64.com/nt/subst.html" title="More about the subst command">subst</a> C: G:\</pre>
<p>There. I started the installer again and had no problem this time!</p>
<p>Way to go Adobe..</p>
<p>PS: Don't ask me how I ended up having <code>G:</code> as the system drive instead of the standard <code>C:</code>.</p>
