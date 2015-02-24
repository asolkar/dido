---
layout: post
status: publish
published: true
title: Vimpress to edit/publish WordPress posts
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 82
wordpress_url: http://tech.mahesha.com/2008/04/13/vimpress-to-editpublish-wordpress-posts/
date: '2008-04-13 22:14:28 -0700'
date_gmt: '2008-04-14 06:14:28 -0700'
categories:
- Uncategorized
tags:
- WordPress
- Vim
comments: []
---
<p>This is very impressive. With <a href="http://friggeri.net/blog/2007/07/13/vimpress" title="Vimpress - Vim Plugin!">Vimpress</a>, you can publish/edit <a href="http://www.wordpress.org" title="WordPress website">WordPress</a> blog posts from within <a href="http://www.vim.org" title="Vim website">Vim</a>, like I am doing now. It works great too. This brings together my favorite editor and my favorite blogging platform... Its been around for a while, I only found out today!</p>
<p>UPDATE:</p>
<p>I did find that the plugin does not play well in Vim compiled with python disabled. Vim throws a lot of errors when loading the vimpress plugin (<code>blog.vim</code> file). Adding the following lines before the <code>command!</code> lines in <code>blog.vim</code> addresses this:</p>
<pre>
if !has("python")
  finish
endif
</pre>
<p>Cheers!</p>
