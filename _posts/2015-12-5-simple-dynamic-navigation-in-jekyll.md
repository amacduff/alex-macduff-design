---
layout: post
title:  "Simple Dynamic Navigation in Jekyll"
date:   2015-12-5 11:00:00
permalink: simple-dynamic-navigation-in-jekyll/
categories: jekyll,trick
excerpt: Creating dynamic navigation menus in Jekyll can be as simple or complicated as you want it to be. I thought I'd share a couple easy methods I learned.
---

## The Problem
When rebuilding my portfolio using Jekyll, one of the challenges I ran into was creating a dynamic navigation menu. I wanted to highlight the link of the page currently being viewed, like so:

![]({{ post.url | prepend: site.baseurl }}/img/blog/dynamic_nav.png)

In the past, I simply hardcoded the navigation menu into every page, so I was able to do something like this:

    <nav>
      <ul>
        <li><a href="index.html" class="current">Work</a></li>
        <li><a href="info.html">Info</a></li>
        <li><a href="blog.html">Blog</a></li>
      </ul>
    </nav>

This method is simple, but requires that it be specified on each page which menu link is "current." That's hardly universal. If you move this navigation menu into a header included on every page of the site, you run into problems, because you can no longer declare which is the "current" page.

## The page.url Method
One solution I found (which unfortunately I can't find now, otherwise I'd give credit) was to add an if statement to each link, telling it to check the current page's url against the link's, and if the two match, to add a class of "current".

    {% raw %}<nav>
      <ul>
        <li><a href="{{ site.baseurl }}/index.html" {% if page.url == '/index.html' %} class="current" {% endif %}>Work</a></li>
        <li><a href="{{ site.baseurl }}/info.html" {% if page.url == '/info.html' %} class="current" {% endif %}>Info</a></li>
        <li><a href="{{ site.baseurl }}/blog.html" {% if page.url == '/blog.html' %} class="current" {% endif %}>Blog</a></li>
      </ul>
    </nav>{% endraw %}

This is a pretty simple option, and I think it could work well for a small site with just a few pages. Unfortunately it wasn't quite right for me, for a couple of reasons:

- It requires .html extensions to match the url, so it doesn't work with pretty links (links without the .html extension).
- I wanted to highlight the blog link when viewing any blog post, not just the most recent one (displayed at /blog.html).

## The page.category Method
After a bit of thought I decided to give something a try, just for fun, to see if it worked. And it did! I altered the if statement to check the current page's category, and if it matches a certain category (specified in the if statement) then it adds a class of "current".

    {% raw %}<nav>
      <ul>
        <li><a href="{{ site.baseurl }}/" {% if page.category == 'work' %} class="current"{% endif %}>Work</a></li>
        <li><a href="{{ site.baseurl }}/info" {% if page.category == 'info' %} class="current"{% endif %}>Info</a></li>
        <li><a href="{{ site.baseurl }}/blog" {% if page.category == 'blog' %} class="current"{% endif %}>Blog</a></li>
      </ul>
    </nav>{% endraw %}

One downside to this method is that you have to add a category to the front matter of each of your pages. To avoid having to add a category of "blog" to each and every blog post, I added it to the front matter of the post layout, which I use for all my blog posts.

## In Summary
This is probably not the best way to achieve this effect, but it worked for me, for whatever that's worth. I've got a lot to learn about Jekyll, and code in general, and I want to share as I learn and grow.

Got a better solution? <a href="mailto:hello@alexmacduff.com?subject=I%20am%20a%20Jekyll%20master">Email me!</a> I'd love to update this blog post (and give you credit, of course).
