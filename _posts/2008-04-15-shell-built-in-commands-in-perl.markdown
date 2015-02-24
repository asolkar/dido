---
layout: post
status: publish
published: true
title: Shell built-in commands in Perl script
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 83
wordpress_url: http://tech.mahesha.com/?p=83
date: '2008-04-15 13:35:46 -0700'
date_gmt: '2008-04-15 21:35:46 -0700'
categories:
- Uncategorized
tags:
- Perl
- Shell
- Unix
comments: []
---
<p>There's been a lot of people on the <a href="http://blogsearch.google.com/blogsearch?ie=UTF-8&oe=utf-8&client=firefox-a&um=1&q=history+awk&as_maxm=4&as_miny=2008&as_maxy=2008&as_minm=4&as_mind=8&as_maxd=15&as_drrb=b&ctz=420&c1cr=4%2F8%2F2008&c2cr=4%2F15%2F2008&btnD=Go" title="Recent blog entries">blogosphere</a> reporting shell history. The idea is to know what kind of commands different people use on their shell - kinda geeky, but none the less. Here's the command most are using:</p>
<pre>
  history|awk '{a[$2]++ } END{for(i in a){print a[i] " " i}}'|sort -rn|head
</pre>
<p>A Perl enthusiast that I am, I started out to do the same in Perl instead of <code>awk</code>. I started writing a script <code>hotlist</code> that will get the shell history, count unique commands and sort them in descending order of the count. Seems very straightforward. Turns out, its only straightforward - without the <em>very</em>.</p>
<p>Since <code>history</code> is a built-in shell command, it cannot called it with the <a href="http://perldoc.perl.org/perlop.html#qx/STRING/" title="`STRING`"><code>qx//</code> or back-tick (<code>``</code>) syntax of Perl</a> to fetch shell history. I resorted to <a href="http://www.google.com" title="Google search">Google</a> to find a solution, but could not find one easily. After some help from <a href="http://groups.google.com/group/comp.lang.perl.misc/topics?hl=en" title="comp.lang.perl.misc">clpm</a>, I came up with this:</p>
<pre>
#!/usr/bin/perl

use strict;
use warnings;

my %hist = (); 
my @hist;

$hist{(split /\s+/)[3]}++
  foreach ((-p STDIN) ? &lt;STDIN&gt; : `$ENV{'SHELL'} -c history`);

print map {"$hist{$_} : $_\n"} 
        sort {$hist{$b} &lt;=&gt; $hist{$a}} 
          keys %hist;
</pre>
<p>To use shell's built-in commands, you must invoke the shell and have it execute the built-in command. In the above script, that is done with <code>`$ENV{'SHELL'} -c history`</code>, which in my case expands to <code>`/usr/local/bin/tcsh -c history`</code> since I use t-shell. The shell can be invoked by <code>qx//</code> or back-tick (<code>``</code>) to collect the output.</p>
<p>You can use this script in two flavors:</p>
<pre>
  % hotlist
  % history | hotlist
</pre>
<p>The first flavor starts a new shell and calls the <code>history</code> command in it. So you get the information from saved shell history. It does not contain commands form the active shell. If you want to include the active shell too, use the second flavor. Where you pipe the current shell's history into the script.</p>
<p>Hopefully, this will help the next person who wants to use shell built-in commands in Perl. Like I said, I am a Perl enthusiast, not an expert, so this may not be the best solution.</p>
<p>I am sure some Perl guru will manage to cram all that in a one-liner, but that was not my intent.</p>
