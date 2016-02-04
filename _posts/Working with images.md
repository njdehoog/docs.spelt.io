---
layout: post
title: Working with images
date: 2015-01-29 12:45:18 +0100
category: writing
permalink: images
---

When writing your blog posts, you'll likely want to include images at some point. A common solution is to create an `img` or `assets/img` directory in your project folder. Because of the way Spelt works, this folder will be copied as is to your generated site (this is explained in [directory structure](/directory-structure/)).

Let's say you've created an `img` folder in your project directory and copied some images over. You can now reference these images in your blog posts like this:

<pre><code>![Hiker](&#123;&#123; site.url }}/img/hiker.jpg)</code></pre>

And they will appear on your site like this:

![Hiker](/img/hiker.jpg)

> Tip: if you know your site will only ever be hosted at the root URL of your domain, e.g. http://example.com and __not__ http://example.com/blog, you can skip the <code>&#123;&#123; site.url }}</code> part and just use: `/img/hiker.jpg` as the path.