---
title:  "Udacity: Blog"
sub-title: "Creating a secure multi-user-blog"
short-description: "This was part of an assignment at Udacity. The goal was to create a working blog, where users could publish blog-posts and manage them. Voting, editing and secure logins are of course baked in."
date:   2017-04-05 23:02:20 +0100
categories: software
tags: Udacity blog
image: "my_blog.png"
image_description: "Blog screenshot"
---


<h3>Blog <small> &mdash; Creating a secure multi-user-blog</small></h3>

This is part of an assignment in the Full-Stack-course at Udacity. The goal is to create a multi-user-blog, deployed using Google App Engine.

The project can be seen at [Causal-destiny-157016.appspot.com](http://causal-destiny-157016.appspot.com) and the code at [my_blog github repo](https://github.com/runartrollet/my_blog)

<div class="center">{% include image.html alt="Blog screenshot" image="my_blog.png"  class="center col-6" sizes="(min-width: 800px) 50vw, 100vw"%}</div>

## Rundown of features:

- Secure userhandling with hashing and salting.
- Users can post blogs, and comment on any post.
- They can edit content they themselves created.
- Users can vote on posts, but not on their own.
