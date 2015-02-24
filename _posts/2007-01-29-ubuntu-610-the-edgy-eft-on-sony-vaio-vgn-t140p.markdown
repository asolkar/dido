---
layout: post
status: publish
published: true
title: Ubuntu 6.10 (the Edgy Eft) on Sony Vaio VGN-T140P
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 17
wordpress_url: http://tech.mahesha.com/2007/01/29/ubuntu-610-the-edgy-eft-on-sony-vaio-vgn-t140p/
date: '2007-01-29 09:55:49 -0800'
date_gmt: '2007-01-29 17:55:49 -0800'
categories: []
tags:
- OS
- Linux
comments:
- id: 3
  author: Day in, day outâ€¦ &raquo; Blog Archive &raquo; Ubuntu 6.10 on Sony VAIO
    VGN-T140P
  author_email: ''
  author_url: http://tech.mahesha.com/2007/01/16/ubuntu-610-on-sony-vaio-vgn-t140p/
  date: '2007-01-29 10:02:52 -0800'
  date_gmt: '2007-01-29 18:02:52 -0800'
  content: '[...] UPDATE: Please refer to a more detailed account of this installation
    for more information [...]'
- id: 24
  author: But oh, the wasted hours&#8230;
  author_email: ''
  author_url: http://tech.mahesha.com/2007/04/26/but-oh-the-wasted-hours/
  date: '2007-04-26 11:09:55 -0700'
  date_gmt: '2007-04-26 19:09:55 -0700'
  content: '[...] Few months back when I installed Edgy on my Sony laptop, audio wasn&#8217;t
    working right out of the box. I had to spend a few days googling and ubuntu-forumming
    to find the fix for that. Eventually it worked fine after un-muting some channels
    in the Volume Control. [...]'
- id: 55
  author: Sony Sound
  author_email: sony@flt.co.nz
  author_url: ''
  date: '2008-06-01 15:46:23 -0700'
  date_gmt: '2008-06-01 23:46:23 -0700'
  content: THANKS SO MUCH - your info worked a treated for the sound
- id: 1187
  author: USB 3G Viettel
  author_email: ankhanh3@mailinator.com
  author_url: http://usb3gvn.com/
  date: '2012-01-06 02:51:00 -0800'
  date_gmt: '2012-01-06 10:51:00 -0800'
  content: I am really glad I read this article! With this it has really helped me
    with my decision.
- id: 1188
  author: Web Hosting Provider
  author_email: shiv.1935@yahoo.com
  author_url: http://www.webhostings.in/
  date: '2012-01-24 03:21:00 -0800'
  date_gmt: '2012-01-24 11:21:00 -0800'
  content: Excellent information you have shared here and i got great and huge knowledge
    about this concept
---
<p>I mentioned in one of the <a href="http://tech.mahesha.com/2007/01/16/ubuntu-610-on-sony-vaio-vgn-t140p/trackback/" title="Ubuntu 6.10 on Sony VAIO VGN-T140P">previous posts</a> that I will reinstall Ubuntu from scratch and document the process in more detail than I did last time. Well, here it is!</p>
<p>It took roughly couple of hours to get back to where I was after the last installation. There were the same issues as last time after a clean install, and I knew exactly what to do to fix them. More than week of googling and trying different things helped this install go much faster.</p>
<p>Before I reinstalled 6.10, I gave 7.04 alpha (the Feisty Fawn) a shot. It was good for most part, but had major issues with hibernate and response to power button behavior. I decided to go back to a more stable 6.10.</p>
<p>Output of <code>lspci</code> and <code>lsmod</code> are near the end of this post. And here's the installation process:</p>
<p><strong>Dual Boot</strong></p>
<p>I wanted to keep Windows XP alongside Ubuntu on this laptop. So I partitioned the hard disc with Symantec Partition Magic 8. Created one Ext3 (approximately 13GB) and one Swap (little above 1GB) partition for Linux install. PM8 has the capabilities to create Ext3  and Linux Swap partitions.</p>
<p><strong>Clean Install</strong></p>
<p>I downloaded <a href="http://cdimage.ubuntu.com/releases/edgy/release/" title="Ubuntu downloads page">Ubuntu 6.10</a> Live CD image. Restarted the Vaio with the disc in the CD drive. Selected to 'Run Live CD/Install'. After the desktop was up, I double-clicked on the <em>install</em> icon. That started the installation process. After answering a few easy questions, installation was on its way. Since I was using dual-boot, I had to make sure I am using correct partitions for Linux installation. This process took about 20-30 minutes.</p>
<p>After the installation process was done, I restarted the machine. On restart, I was given the choice to load Linux or Windows - I selected Linux (its all about making the right choice baby ;) ).</p>
<p><strong>Wireless LAN (WPA)</strong></p>
<p>First thing I had to bring up was networking, so that I could install updates and modules I needed to fix other issues. I use <acronym title="Wi-Fi Protected Access">WPA</acronym> for authentication. I created <code>/etc/wpa_supplicant.conf</code> file with following contents:</p>
<pre>
    ap_scan=2
    network={
      ssid="myssid"
      psk="mypassphrase"
      key_mgmt=WPA-PSK
      proto=WPA
      pairwise=TKIP
    }
</pre>
<p>Then added following lines to the <code>/etc/network/interfaces</code> file:</p>
<pre>
    auto eth1
    iface eth1 inet dhcp
    pre-up wpa_supplicant -Bw -Dwext -ieth1 -c/etc/wpa_supplicant.conf
    post-down killall -q wpa_supplicant
</pre>
<p>After I restarted the machine, wireless LAN was up and running. I added the <em>Network Monitor</em> applet to to a panel to monitor the <code>eth1</code> connection.</p>
<p><strong>Widescreen  LCD</strong></p>
<p>The thing that was still bugging me was that widescreen aspect ratio of the screen was not being used. I had to install the <code>915resolution</code> package to get that right.</p>
<p>I opened the <em>System -> Administration-> Synaptic Package Manager</em> and installed the required module (after the required authentication).</p>
<p>After a restart, widescreen format was automatically detected and configured.</p>
<p><strong>Audio</strong></p>
<p>The computer was silent after the clean install. I found some help on <a href="http://www.ubuntux.org/no-sound-on-ubuntu-dapper" title="No sound on Ununtu Dapper">ubuntux.org</a> that helped me resolve my sound related problem.</p>
<p>I opened the <em>Volume Control</em> by double-clicking on the speaker icon in the panel. Un-muted every control in 'Playback' and 'Capture' and put the slider control somewhere in the middle for every output and input. Then I went to <em>Edit->Preference</em>, checked 'Headphone Jack Sense', 'Line Jack Sense' and 'External Amplifier' boxes. Back in the main window under 'Switches', unchecked 'Headphone Jack Sense', 'Line Jack Sense' and 'External Amplifier'.</p>
<p>That was all I needed to get the audio working.</p>
<p><strong>Touchpad</strong></p>
<p>I customized Synaptics Touchpad to suit me. I turned OFF right-top and right-bottom corners, they were causing unintentional right-clicks and pastes. This is how my <em>InputDevice</em> section in <code>/etc/X11/xorg.conf</code> looks:</p>
<pre>
Section "InputDevice"
  Identifier "Synaptics Touchpad"
  Driver "synaptics"
  Option "SendCoreEvents"    "true"
  Option "Device"            "/dev/psaux"
  Option "Protocol"          "auto-dev"
  Option "HorizScrollDelta"  "0"
  Option "RightEdge"         "950"
  Option "MaxTapTime"        "225"
  Option "MaxTapMove"        "160"
  Option "MaxDoubleTapTime"  "225"
  Option "SingleTapTimeout"  "180"
  Option "MinSpeed"          "0.40"
  Option "MaxSpeed"          "0.90"
  Option "AccelFactor"       "0.0060"
  Option "RTCornerButton"    "0"
  Option "RBCornerButton"    "0"
  Option "SHMConfig"         "on"
EndSection
</pre>
<p><strong>Applications</strong></p>
<p>Ubuntu 6.10 comes with a few applications that I usually use like, Firefox 2.0 and Gaim. Next, I installed all the applications I need for day to day work and fun. All these are available via <em>Synaptic Package Manager</em></p>
<ul>
<li><strong>gVim</strong>: Available in <code>vim-gname</code> package. I use the GUI version of vim for most of my editing/programming work</li>
<li><strong>Banshee</strong>: Available in code>banshee</code> package. I found this to be a decent MP3 playback and music library management application</li>
<li><strong>Ogle</strong>: DVD playback on Linux is a big pain. No single application/plugin plays all my DVDs well. Ogle plays some that I created myself pretty well. But it couldn't play the ones that I bought (encrypted?). Available in the <code>ogle-gui</code> package. I followed <a href="http://www.linuxforums.org/forum/ubuntu-help/70234-totem-could-not-play-dvd-media-cdrom0.html#2" title="Xine instead of Gstreamer for Totem">more instructions</a> to use xine instead of gstreamer plugin for Totem, to play some DVDa that ogle does not play</li>
<li><strong>GNUstep</strong>: Framework, more than an application. I am learning Objective-C programming with GNUstep, so all my current fun projects use this. Available in <code>gnustep-*devel*</code> packages.</li>
</ul>
<p>Like many blog posts helped me during my Linux installation, I hope someone finds this post helpful.</p>
<hr>
<strong>Output of <code>lspci</code></strong>:</p>
<pre>
00:00.0 Host bridge: Intel Corporation 82852/82855 GM/GME/PM/GMV Processor to I/O Controller (rev 02)
00:00.1 System peripheral: Intel Corporation 82852/82855 GM/GME/PM/GMV Processor to I/O Controller (rev 02)
00:00.3 System peripheral: Intel Corporation 82852/82855 GM/GME/PM/GMV Processor to I/O Controller (rev 02)
00:02.0 VGA compatible controller: Intel Corporation 82852/855GM Integrated Graphics Device (rev 02)
00:02.1 Display controller: Intel Corporation 82852/855GM Integrated Graphics Device (rev 02)
00:1d.0 USB Controller: Intel Corporation 82801DB/DBL/DBM (ICH4/ICH4-L/ICH4-M) USB UHCI Controller #1 (rev 03)
00:1d.1 USB Controller: Intel Corporation 82801DB/DBL/DBM (ICH4/ICH4-L/ICH4-M) USB UHCI Controller #2 (rev 03)
00:1d.2 USB Controller: Intel Corporation 82801DB/DBL/DBM (ICH4/ICH4-L/ICH4-M) USB UHCI Controller #3 (rev 03)
00:1d.7 USB Controller: Intel Corporation 82801DB/DBM (ICH4/ICH4-M) USB2 EHCI Controller (rev 03)
00:1e.0 PCI bridge: Intel Corporation 82801 Mobile PCI Bridge (rev 83)
00:1f.0 ISA bridge: Intel Corporation 82801DBM (ICH4-M) LPC Interface Bridge (rev 03)
00:1f.1 IDE interface: Intel Corporation 82801DBM (ICH4-M) IDE Controller (rev 03)
00:1f.3 SMBus: Intel Corporation 82801DB/DBL/DBM (ICH4/ICH4-L/ICH4-M) SMBus Controller (rev 03)
00:1f.5 Multimedia audio controller: Intel Corporation 82801DB/DBL/DBM (ICH4/ICH4-L/ICH4-M) AC'97 Audio Controller (rev 03)
00:1f.6 Modem: Intel Corporation 82801DB/DBL/DBM (ICH4/ICH4-L/ICH4-M) AC'97 Modem Controller (rev 03)
02:04.0 CardBus bridge: Texas Instruments PCI7420 CardBus Controller
02:04.2 FireWire (IEEE 1394): Texas Instruments PCI7x20 1394a-2000 OHCI Two-Port PHY/Link-Layer Controller
02:04.3 Mass storage controller: &lt:pci_lookup_name: buffer too small&gt;
02:08.0 Ethernet controller: Intel Corporation 82801DB PRO/100 VE (MOB) Ethernet Controller (rev 83)
02:0b.0 Network controller: Intel Corporation PRO/Wireless 2200BG Network Connection (rev 05)
</pre>
<p><strong>Output of <code>lsmod</code></strong>:</p>
<p>Now, that's a long list. I am sure there are some modules that I don't use at all. How do I find out which ones? How do I stop them from loading?</p>
<pre>
Module                  Size  Used by
battery                11652  0 
ac                      6788  0 
thermal                15624  0 
fan                     6020  0 
button                  7952  0 
ipw2200               115652  0 
ieee80211              35272  1 ipw2200
e100                   38020  0 
mii                     6912  1 e100
isofs                  38076  0 
udf                    89348  0 
ipv6                  272288  8 
binfmt_misc            13448  1 
rfcomm                 42260  0 
l2cap                  27136  5 rfcomm
sonypi                 24252  0 
i915                   21632  2 
drm                    74644  3 i915
speedstep_centrino      9760  1 
cpufreq_userspace       5408  0 
cpufreq_stats           7744  0 
freq_table              6048  2 speedstep_centrino,cpufreq_stats
cpufreq_powersave       2944  0 
cpufreq_ondemand        8876  1 
cpufreq_conservative     8712  0 
video                  17540  0 
tc1100_wmi              8324  0 
sony_acpi               6412  0 
sbs                    16804  0 
pcc_acpi               14080  0 
i2c_ec                  6272  1 sbs
i2c_core               23424  1 i2c_ec
hotkey                 11556  0 
dev_acpi               12292  0 
container               5632  0 
asus_acpi              17688  0 
michael_mic             3712  4 
arc4                    3200  4 
ieee80211_crypt_tkip    12416  2 
nls_utf8                3200  1 
ntfs                  112116  1 
sbp2                   24584  0 
scsi_mod              144648  1 sbp2
parport_pc             37796  0 
lp                     12964  0 
parport                39496  2 parport_pc,lp
af_packet              24584  6 
pcmcia                 40380  0 
joydev                 11200  0 
ieee80211_crypt         7552  2 ieee80211,ieee80211_crypt_tkip
yenta_socket           28812  1 
rsrc_nonstatic         15360  1 yenta_socket
pcmcia_core            43924  3 pcmcia,yenta_socket,rsrc_nonstatic
snd_intel8x0           34844  1 
snd_ac97_codec         97696  1 snd_intel8x0
snd_ac97_bus            3456  1 snd_ac97_codec
snd_pcm_oss            47360  0 
snd_mixer_oss          19584  1 snd_pcm_oss
snd_pcm                84612  3 snd_intel8x0,snd_ac97_codec,snd_pcm_oss
snd_timer              25348  1 snd_pcm
tsdev                   9152  0 
hci_usb                18068  0 
bluetooth              53476  5 rfcomm,l2cap,hci_usb
psmouse                41352  0 
snd                    58372  8 snd_intel8x0,snd_ac97_codec,snd_pcm_oss,snd_mixer_oss,snd_pcm,snd_timer
soundcore              11232  1 snd
evdev                  11392  2 
serio_raw               8452  0 
snd_page_alloc         11400  2 snd_intel8x0,snd_pcm
shpchp                 42144  0 
pci_hotplug            32828  1 shpchp
intel_agp              26012  1 
agpgart                34888  3 drm,intel_agp
ext3                  142728  1 
jbd                    62228  1 ext3
ohci1394               37040  0 
ieee1394              306104  2 sbp2,ohci1394
ehci_hcd               34696  0 
uhci_hcd               24968  0 
usbcore               134912  4 hci_usb,ehci_hcd,uhci_hcd
ide_generic             2432  0 
ide_cd                 33696  0 
cdrom                  38944  1 ide_cd
ide_disk               18560  4 
piix                   11780  1 
generic                 6276  0 
processor              31560  2 thermal,speedstep_centrino
fbcon                  41504  0 
tileblit                3840  1 fbcon
font                    9344  1 fbcon
bitblit                 7168  1 fbcon
softcursor              3328  1 bitblit
vesafb                  9244  0 
capability              5896  0 
commoncap               8704  1 capability
</pre>
