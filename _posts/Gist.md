---
layout: post
title: Embedding GitHub Gists
date: 2013-02-05 10:44:04 +0100
permalink: gists
category: writing
---

Besides supporting code snippets using regular [Markdown syntax](/markdown/#code-snippets), Spelt also defines a custom tag for Stencil which allows you to easily embed a GitHub Gist in your blog posts. All you need to do is copy and paste the Gist's ID from the URL.

<pre><code>&#123;% gist cb9651c70c322b720b41 %}</code></pre>

## The World's Last C Bug

The code snippet from above would produce the following:

{% gist cb9651c70c322b720b41 %}