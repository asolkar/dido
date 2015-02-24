---
layout: post
status: publish
published: true
title: Ubuntu 6.10 on Sony VAIO VGN-T140P
author:
  display_name: mahesha
  login: admin
  email: mahesha.com@gmail.com
  url: http://mahesha.com
author_login: admin
author_email: mahesha.com@gmail.com
author_url: http://mahesha.com
wordpress_id: 14
wordpress_url: http://tech.mahesha.com/2007/01/16/ubuntu-610-on-sony-vaio-vgn-t140p/
date: '2007-01-16 01:29:08 -0800'
date_gmt: '2007-01-16 09:29:08 -0800'
categories: []
tags:
- OS
- Linux
comments:
- id: 2
  author: Day in, day outâ€¦ &raquo; Blog Archive &raquo; Ubuntu 6.10 (the Edgy Eft)
    on Sony Vaio VGN-T140P
  author_email: ''
  author_url: http://tech.mahesha.com/2007/01/29/ubuntu-610-the-edgy-eft-on-sony-vaio-vgn-t140p/
  date: '2007-01-29 09:55:55 -0800'
  date_gmt: '2007-01-29 17:55:55 -0800'
  content: '[...] I mentioned in one of the previous posts that I will reinstall Ubuntu
    from scratch and document the process in more detail than I did last time. Well,
    here it is! [...]'
---
<p><strong>UPDATE</strong>: Please refer to <a href="http://tech.mahesha.com/2007/01/29/ubuntu-610-the-edgy-eft-on-sony-vaio-vgn-t140p/" title="Ubuntu 6.10 (the Edgy Eft) on Sony Vaio VGN-T140P">a more detailed account of this installation</a> for more information</p>
<p>I recently installed Ubuntu 6.10 (The Edgy Eft) on my Sony VAIO VGN-T140P laptop. It dual boots with Windows XP Professional. This installation was the best Linux installation experiences I have had. But it was not as smooth as I had expected - as compared to Mac OS X or Windows - in that basic things should work out of the box. If I am trying to get a specialty video card or a TV tuner card to work, I can expect some experimenting and googling. I was expecting that with the standard hardware that is on this laptop, the installation would be a breeze - it wasn't so.</p>
<p>Here's what is working and what is not:</p>
<dl>
<dt><strong>Widescreen</strong></dt>
<dd>The laptop has a 1280x768 widescreen. Beginning with the Live CD Ubuntu did not auto detect it. I thought it would detect it when installation is done - it did not. The widescreen mode was not even in the options for me to set manually. I had to install 915resolution package to get it working. I used Synaptic Package Manager to install the package. After a restart, the widescreen was detected and properly set.</dd>
<dt><strong>Wireless LAN</strong></dt>
<dd>This was the sweetest surprise. Like I mentioned in an earlier post, I've had more than my share of trouble getting Wireless LAN working in the past. This time it was almost a breeze. Earlier I was using WEP shared Key authentication. I just had to do a little googling to learn that Shared Key does not work all that well. So I ended up using Open System. But later I switched to WPA-PSK TKIP authentication. I installed wpa_supplicant and edited the wpa_supplicant.conf to read:<br />
<code><br />
ap_scan=2<br />
&nbsp;&nbsp;network={<br />
&nbsp;&nbsp;ssid="my_ssid"<br />
&nbsp;&nbsp;psk="my_passphrase"<br />
&nbsp;&nbsp;key_mgmt=WPA-PSK<br />
&nbsp;&nbsp;proto=WPA<br />
&nbsp;&nbsp;pairwise=TKIP<br />
}<br />
</code><br />
Wireless is working like charm since.</p>
</dd>
<dt><strong>Audio</strong></dt>
<dd>This was an unexpected hiccup. I always took audio for granted. I had never had to spend such a long time figuring this out. It turns out, the audio is muted by default! I had to start '/usr/bin/alsamixer' and unmute the Headphone audio. Then in Volume Control preferences, make enough tracks visible so that headphone switch is displayed then check it. The audio works well now</dd>
<dt><strong>DVD, MP3 Playback</strong></dt>
<dd>Another shocker. I'd expect this to work out of the box. I had to try out Totem, Mplayer, gXine... install plugins I don't even remember, to be able to play DVDs. Even MP3 playback wasn't working out of the box. After unsuccessfully trying out plugins for Totem, Mplayer, Noatun, Rythmbox - I ended up installing xmms to get MP3 playback</dd>
<dt><strong>Touch Pad</strong></dt>
<dd> I customized Synaptics Touchpad to suit me. I turned OFF right-top and right-bottom corners, they were causing unintentional right-clicks and pastes. This is how my InputDevice section in /etc/X11/xorg.conf looks:<br />
<code><br />
Section "InputDevice"<br />
&nbsp;&nbsp;Identifier  "Synaptics Touchpad"<br />
&nbsp;&nbsp;Driver      "synaptics"<br />
&nbsp;&nbsp;Option      "SendCoreEvents"        "true"<br />
&nbsp;&nbsp;Option      "Device"                "/dev/psaux"<br />
&nbsp;&nbsp;Option      "Protocol"              "auto-dev"<br />
&nbsp;&nbsp;Option      "HorizScrollDelta"      "0"<br />
&nbsp;&nbsp;Option      "RightEdge"             "950"<br />
&nbsp;&nbsp;Option      "MaxTapTime"            "225"<br />
&nbsp;&nbsp;Option      "MaxTapMove"            "160"<br />
&nbsp;&nbsp;Option      "MaxDoubleTapTime"      "225"<br />
&nbsp;&nbsp;Option      "SingleTapTimeout"      "180"<br />
&nbsp;&nbsp;Option      "MinSpeed"              "0.40"<br />
&nbsp;&nbsp;Option      "MaxSpeed"              "0.90"<br />
&nbsp;&nbsp;Option      "AccelFactor"           "0.0060"<br />
&nbsp;&nbsp;Option      "RTCornerButton"        "0"<br />
&nbsp;&nbsp;Option      "RBCornerButton"        "0"<br />
&nbsp;&nbsp;Option      "SHMConfig"             "on"<br />
EndSection
</pre>
</dd>
<dt><strong>Volume/Multimedia buttons</strong></dt>
<dd>This is something that is still broken. What makes it worse is that I have no clue how to solve this. All the volume and multimedia buttons trigger an event with same keycode. There is no way of distinguishing between volume-up and volume-down buttons. Or any of DVD play/stop/Forward/Backward buttons.</dd>
</dl>
<p>I think I am going to redo the installation so that I can document the problems and solutions in greater detail. May be that will help someone who's facing similar problems!</p>
