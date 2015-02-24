---
layout: post
status: publish
published: true
title: Synchronizing bookmarks
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 163
wordpress_url: http://tech.mahesha.com/?p=163
date: '2009-03-24 23:09:55 -0700'
date_gmt: '2009-03-25 07:09:55 -0700'
categories:
- Uncategorized
tags:
- Firefox
- Google
- Weave
- Delicious
- Bookmarks
comments: []
---
<p>The requirement is simple:</p>
<blockquote><p>It is desirable that when we use our browser on different computers, we want to feel at home on all of the computers. If we bookmark a website on one computer, other computers should also get it seamlessly. If we end up using a loaner computer, the bookmarks should be readily available online. </p></blockquote>
<p>When I say <em>feel at home</em>, I have something very Mozilla Firefox specific in mind. I use <a href="http://www.dria.org/wordpress/archives/2008/04/17/628/" title="Firefox's AwesomeBar">Firefox's smart URL bar</a>, or what is called the AwesomeBar, extensively. When I start typing in the URL bar, I like to get suggestions based on my bookmarks and history. When I get the suggestions, I want them to be derived from the latest and the greatest of my bookmarks - bookmarks added on my current computer, or some other computer. Getting history from the other computer would be great too, but just bookmarks should be just fine.</p>
<p>So what are the options? From what I read, there are quite a few...</p>
<p><strong>Weave</strong><br />
<a href="http://labs.mozilla.com/projects/weave/" title="About Mozilla Labs - Weave"><br />
Weave from Mozilla Labs</a>, to me, is the most promising candidate to solve the problem at hand. But it is far from ready for general consumption. Every new version (that comes out pretty frequently) seems to break something or the other - It is fixed very promptly too - but there is disruption. It is indeed in lab-mode.</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/weave-prefs.png"><img src="http://tech.mahesha.com/wp-content/images/weave-prefs.png" alt="Weave preferences - Click for full size" width="475px"/></a></p>
<div class="caption">Weave synchronizes variety of profile items</div>
</div>
<p>What I like about Weave is that it synchronizes almost your entire Firefox profile between multiple Firefox installations - Bookmarks, History, Tabs, Saved Passwords, may be even more in the future. The data is stored (by default) on Mozilla's servers in an encrypted format, that only your can read. Privacy <del datetime="2009-03-25T00:53:03+00:00">freaks</del> concerned can setup their own servers, so their data stays with them. But then they must keep the server accessible from the internet.</p>
<p>All this is achieved using the <acronym title="User Interface">UI</acronym> elements that already exist in Firefox - namely, the <em>star</em> in the URL bar. It is very intuitive, and in most cases very seamless.</p>
<p>It is really neat.</p>
<p>The down side to weave, is that there is no web interface to the data on the server. So if I am on a loaner computer, or in an internet cafe, my bookmarks are not accessible to me. I cannot use my existing bookmarks. I cannot add a bookmark if I come across something useful.</p>
<p><strong>Delicious</strong></p>
<p><a href="http://delicious.com/" title="Delicious social bookmarking web service">Delicious</a> is one of the most widely used social bookmarking service. <a href="http://delicious.com/help/quicktour/firefox" title="Delicious Firefox add-on">Delicious add-on for Firefox</a> provides an additional bookmarking system where the bookmarks are stored on the Delicious website. The add-on provides handy buttons to manage the online bookmarks.</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/delicious-buttons.png"><img src="http://tech.mahesha.com/wp-content/images/delicious-buttons.png" alt="Buttons added by Delicious addon"/></a></p>
<div class="caption">Delicious adds button that do things similar to Firefox's <em>star</em></div>
</div>
<p>Although the Delicious website says that the add-on <em>enhances Firefox's bookmarking system</em>, in my opinion, it is more like an additional bookmarking system. The add-on adds <acronym title="User Interface">UI</acronym> elements to Firefox toolbar to interact with Delicious bookmarks. A tag button that functions exactly like the <em>star</em> in Firefox's URL bar. A new window to add tags to the new bookmark, where you input almost the same information that you do in Firefox's native interface. A bookmarks menu item, that is very similar to the native Firefox bookmarks menu. There's just too much redundancy.</p>
<p>Since Delicious is mainly an online service, it has a very mature and efficient web interface. And because all your bookmarks are online, you can access them from any computer with an internet connection - whether it is your own or a loaner or one in an internet cafe.</p>
<p><strong>Google Bookmarks</strong></p>
<p><a href="http://www.google.com/bookmarks/" title="Google Bookmarks website">Google Bookmarks</a> is a part of <a href="http://www.google.com/history/" title="Google Web History website">Google Web History</a>. Like Delicious, the bookmarks are saved online and they can be accessed from any online computer.</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/google-tb-buttons.png"><img src="http://tech.mahesha.com/wp-content/images/google-tb-buttons.png" alt="Buttons added by Google Toolbar"/></a></p>
<div class="caption">Google Toolbar adds its own <em>star</em></div>
</div>
<p>Google Bookmarks integrate well with the <a href="http://toolbar.google.com" title="Google Toolbar website">Google Toolbar for Firefox</a>. Also like Delicious, the interface provided by the Google toolbar for bookmarking is exactly like Firefox's own. The toolbar adds its own <em>star</em>, which is used to bookmark a website, or edit (add tags to) an existing bookmark.</p>
<p><strong>Foxmarks A.K.A. Xmarks</strong></p>
<p>Foxmarks which is now known as <a href="http://www.xmarks.com/" title="Foxmarks AKA Xmarks">Xmarks</a> is also a strong contender in this space. It has the goods of both online bookmarking services and native Firefox bookmark synchronizing. Xmarks provides an add-on for Firefox (in addition to Internet Explorer and Safari, which is an added bonus), that just synchronizes your bookmarks with an online storage on xmarks.com. They have a neat web interface to manage the online bookmarks. Any changes made online, or on any computer are automatically synchronized.</p>
<p><strong>The missing link</strong></p>
<p>Although Delicious and Google Bookmarks provide a usable interface with Firefox, there is one deficiency in both of them that is very significant to me (an AwesomeBar user). Bookmarks on Delicious or Google Bookmarks don't become a part of Firefox Bookmarks, and hence are not accounted in the search algorithm used by the AwesomeBar. If I add a bookmark to either of the two services, it will not be suggested when I type something in the URL bar.</p>
<p><strong>Conclusion</strong></p>
<p>I love the fact that online bookmarks (Delicious/Google Bookmarks) are available from anywhere on the internet. However, no matter how much I try to get used to one of the two services, I miss that fact that online bookmark are not included in the AwesomeBar suggestions.</p>
<p>A web interface to manage Weave's bookmarks online will be a welcome feature. Or If add-ons provided by online bookmark services somehow integrate their bookmarks with Firefox's bookmarks, that would be cool too.</p>
<p>Until then, it will have to be an inconvenient combination of the two.</p>
<p>I have not used Xmarks long enough to form a solid opinion about it. I'll just have to play around with it for a while.</p>
<p><em>Edit: Added Foxmarks/Xmarks as a viable alternative, after this post was first written.</em></p>
<p><em>Edit (05/12/2009): Well, looks like the Delicious add-on for Firefox just came a step closer to the way I like it. With its version 2.1.041 released yesterday (?) delicious bookmarks are now integrated with the AwesomeBar. In addition, if you start typing in the address bar with <b>??</b>, AwesomeBar will show only Delicious bookmarks. If you start typing with <b>&gt;&gt;</b>, AwesomeBar will show Delicious tags. This is great! Now if it could just reuse Firefox's native UI elements...</em></p>
