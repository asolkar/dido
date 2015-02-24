---
layout: post
status: draft
title: My thoughts on Tumblr API v2
author:
  display_name: Mahesh Asolkar
  login: Mahesh
  email: mahesh@mahesha.com
  url: http://profiles.google.com/104769499705387203231/about
author_login: Mahesh
author_email: mahesh@mahesha.com
author_url: http://profiles.google.com/104769499705387203231/about
wordpress_id: 528
wordpress_url: http://tech.mahesha.com/?p=528
date: '2011-07-20 21:39:59 -0700'
categories:
- Uncategorized
tags: []
comments: []
---
<p><strong>Paging</strong></p>
<p>There are multiple methods to fetch stream of posts. E.g., <code>/user/dashboard</code>, <code>/posts</code>, <code>/posts/queue</code>, <code>/posts/drafts</code>, <code>/posts/submission</code>, etc. There is no defined way of fetching these streams in pages.</p>
<p>Documentation of <code>/user/dashboard</code> does mention the use of since_id and limit parameters to get pages of posts. However, that will only work if you start from oldest to newest posts (increasing ID numbers). Most often, I want to start from the newest post and fetch older ones as required, <code>since_id</code> and <code>limit</code> parameters don’t work in that context.</p>
<p>Another way to paginate posts is to use offset and limit parameters. Although this approach could result in repeated posts in pages. If I fetch the first page containing posts 0 to 19. Then after half an hour, I go to the next page, and fetch posts 20 to 39. If, within that half hour, another 3 posts were added to my dashboard, posts 20 through 22 will actually return offset 17 through 19 from the first page all over again.</p>
<p><strong>Too many API calls</strong></p>
<p>Intent is to display a list of posts from the dashboard and add ability to like, reblog, delete, etc. each post in the list. Here’s the sequence of events that need to happen:</p>
<ol>
<li>User <code>/user/dashboard</code> to fetch list of posts</li>
<li>Reblog information about posts in the dashboard is not available in the response. So a separate request to <code>/posts?id={post_id}&reblog_info=true</code>, needs to be made per post. I have noticed that <code>reblog_info=true</code> does not work with <code>/user/dashboard</code> method.</li>
<li>It is nice to show the blog avatar per post. However, avatar URL is not included in the blog object within the post object. So a separate request to <code>/avatar</code> method needs to be made, again per post.</li>
</ol>
<p>For a list of 20 posts, that makes it 41 API calls (1 to <code>/user/dashboard</code> method, 20 to <code>/posts</code> method and 20 to <code>/avatar</code> method.</p>
<p>To address this, following changes could be made to the API:</p>
<ol>
<li>Support <code>reblog_info=true</code> with <code>/user/dashboard</code> method as documented</li>
<li>Add <code>blog_info=true</code> support for <code>/user/dashboard</code> method so that blog object is sent within each post object</li>
<li>Include avatar URL in the blog object</li>
</ol>
<p><strong>Reblog info</strong></p>
<p>If <code>reblog_info=true</code> parameter is provided to <code>/posts</code> method, original post’s name, title and URL are returned within the post object. I wonder if ID of the original post could be included too. That way I can fetch any information about that post I want, not just name, title and URL.</p>
<p><strong>Liked posts</strong></p>
<p>There is a <code>/user/likes</code> method to query posts liked by the authenticated user. It would be nice to have something like <code>like_info=true</code> for <code>/user/dashboard</code> method so that each post object in the response has a <code>liked=true</code> value indicating that the authenticated user liked that post.</p>
