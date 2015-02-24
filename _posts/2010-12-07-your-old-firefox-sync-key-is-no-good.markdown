---
layout: post
status: publish
published: true
title: Your old Firefox Sync key is no good!
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 438
wordpress_url: http://tech.mahesha.com/?p=438
date: '2010-12-07 20:04:23 -0800'
date_gmt: '2010-12-08 04:04:23 -0800'
categories:
- Uncategorized
tags:
- Firefox
- Mozilla
- Sync
comments:
- id: 698
  author: SilverWave
  author_email: silverwav@gmail.com
  author_url: http://silverwav.wordpress.com/
  date: '2010-12-11 05:02:21 -0800'
  date_gmt: '2010-12-11 13:02:21 -0800'
  content: "Thanks man :-)\r \n\r \nI needed to update syn here first.\r \n\r  <a
    href=\"https://services.mozilla.com/sync/updated/?version=1.5&amp;channel=dev\"
    rel=\"nofollow\">https://services.mozilla.com/sync/updated/?versio...</a> "
---
<p>After a recent upgrade of Minefield (<a href="http://nightly.mozilla.org">nightly trunk version</a> of Mozilla Firefox) my <a href="http://www.mozilla.com/en-US/firefox/sync/">Sync</a> was completely broken. All I got was the following error message when I started Minefield:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/wrong_sync_key.png"><img src="http://tech.mahesha.com/wp-content/images/wrong_sync_key.png" alt="Wrong Sync Key error - Click for full size"></a></p>
<div class="caption">Wrong Sync Key error</div>
</div>
<p>One installation of Firefox kept working fine for me, all the others failed to sync after that particular update.</p>
<p>It turns out, the old Sync Key we all cherry picked is no good. A Minefield update probably changed my key to a longer, harder-to-remember key - I must say without any indication/notification. I reckon harder-to-remember also means harder-to-guess, so its a good thing for the security of my data in the cloud. However, on the flip side, I will need to print the key and keep it is some safe place - there's no way I am going to remember that one! Or even better, I'll put it in my <a href="https://www.passpack.com/online/">Passpack</a>.</p>
<p>Once I figured that the <em>Wrong Sync Key</em> error was not because of broken Minefield, but because Minefield indeed changed my key, I could quickly bring all the other installations of Firefox in sync again.</p>
<p>All that needs to be done is, grab your new key like so:</p>
<ul>
<li>Open <em>Minefield (or Firefox) button</em> &rarr; <em>Options</em> &rarr; <em>Options</em> (Which is <em>Minefield (or Firefox) button</em> &rarr; <em>Preferences</em> &rarr; <em>Preferences</em> in Linux).</li>
<li>Go to the <em>Sync</em> tab</li>
<li>Expand the <em>Manage Account</em> group</li>
<li>Click on the <em>My Sync Key</em> item</li>
<li>Copy/Print/Write down/Passpack your Sync Key displayed in the dialog that shows up</li>
</ul>
<p>Then in the installation of Firefox where you get the <em>Wrong Sync Key</em> error, update the Sync Key with the new key. This pretty much involves resetting Sync information and setting it up anew, like so:</p>
<ul>
<li>Open <em>Minefield (or Firefox) button</em> &rarr; <em>Options</em> &rarr; <em>Options</em> (Which is <em>Minefield (or Firefox) button</em> &rarr; <em>Preferences</em> &rarr; <em>Preferences</em> in Linux).</li>
<li>Go to the <em>Sync</em> tab</li>
<li>Expand the <em>Manage Account</em> group</li>
<li>Click on the <em>Stop Using This Account</em> item</li>
<li>Select <em>Reset All Information</em> in the dialog that shows up.</li>
<li>Now setup Sync afresh in the Sync Preferences - using the new <em>Sync Key</em></li>
</ul>
<p>I hope when this changes makes into the Beta, there will be a proper notification and process to upgrade the keys in all Firefox installation. Until then, hope this helps...</p>
