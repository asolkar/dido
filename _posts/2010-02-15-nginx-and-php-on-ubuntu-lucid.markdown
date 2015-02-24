---
layout: post
status: publish
published: true
title: Nginx and PHP on Ubuntu Lucid
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 353
wordpress_url: http://tech.mahesha.com/?p=353
date: '2010-02-15 22:45:13 -0800'
date_gmt: '2010-02-16 06:45:13 -0800'
categories:
- Uncategorized
tags:
- Ubuntu
- Nginx
- PHP
- FastCGI
comments:
- id: 585
  author: Kevin
  author_email: ''
  author_url: ''
  date: '2010-06-08 20:04:29 -0700'
  date_gmt: '2010-06-09 04:04:29 -0700'
  content: 'Helpful! Thank you. '
---
<p>To do some PHP development (read experimenting) on my laptop I wanted to get a web-server with PHP running on it. Since this is a laptop with limited resources, I decided to try <a href="http://nginx.org/">Nginx</a> instead of <a href="http://httpd.apache.org/">Apache</a>. Nginx is known to use less memory as compared to Apache. I am hoping this will keep the laptop still usable while the web-server is still running in the background.</p>
<p>This is not an exhaustive how-to, but this is how I installed all that is needed to get my first PHP page up.</p>
<p>Let me begin by mentioning that this laptop currently runs the development build of <a href="http://cdimage.ubuntu.com/releases/lucid/alpha-2/">Ubuntu Lucid</a> (which will become Ubuntu 10.04 LTS sometime in April 2010).</p>
<p>To begin, I installed following packages from Ubuntu Lucid repositories:</p>
<pre>
  % sudo aptitude install nginx php5-cgi lighttpd
</pre>
<p>Although I am not using <code>lighttpd</code>, the package is required because it provides the <code>spawn-fcgi</code> script.</p>
<p>Nginx supports <a href="http://www.fastcgi.com/">FastGI</a> natively. PHP is served as a FastCGI process. </p>
<p>Modify <code>/etc/php5/cgi/php.ini</code> to include the following line:</p>
<pre>
cgi.fix_pathinfo=1
</pre>
<p>Setting this configuration makes sure that PHP sets path information of the executing script in a way that conforms with CGI specifications. The line may already exist in the file, but commented. Just un-comment it. This is an optional step (at least in Lucid version of PHP) since the default value of <code>cgi.fix_pathinfo</code> is 1.</p>
<p>To spawn FastCGI add the following line to <code>/etc/rc.local</code> every time the computer starts.</p>
<pre>
/usr/bin/spawn-fcgi \
    -a 127.0.0.1 -p 9000 -u www-data -g www-data \
    -f /usr/bin/php5-cgi -P /var/run/fastcgi-php.pid
</pre>
<p>This script (<code>spawn-fcgi</code>) was installed via the <code>lighttpd</code> package.</p>
<p>Finally, I configured a website in Nginx and enabled PHP via FastCGI. This configuration would typically reside in <code>/etc/nginx/sites-available/&lt;website_name&gt;</code>:</p>
<pre>
server {
  listen   80;
  server_name  localhost;

  access_log  /var/log/nginx/localhost.access.log;

  root   /var/www/blog;
  index  index.php;
  fastcgi_index  index.php;

  #
  # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
  #
  location ~ \.php$ {
    fastcgi_pass   127.0.0.1:9000;
    fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
    include /etc/nginx/fastcgi_params;
  }
}
</pre>
<p>When all is set up properly, you can test it with the <a href="http://php.net/manual/en/function.phpinfo.php#function.phpinfo.examples"><code>phpinfo()</code> command</a>. It should look something like the following:</p>
<div class="img_container">
<a href="http://tech.mahesha.com/wp-content/images/nginx_fastcgi_phpinfo.png"><img src="http://tech.mahesha.com/wp-content//images/nginx_fastcgi_phpinfo.png" alt="phpinfo() screen - Click for full size" width="475px"></a></p>
<div class="caption">phpinfo() screen with Nginx+PHP setup</div>
</div>
<p>All this, mostly a note to self. But hope it helps someone out there.</p>
