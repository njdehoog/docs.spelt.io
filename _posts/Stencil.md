---
layout: post
title: Layouts
date: 2016-01-29 13:42:45 +0100
category: templates
permalink: layouts
---

Spelt uses a customized version of [Stencil](https://github.com/kylef/Stencil) as its templating language. By setting the `layout` parameter in the [front matter](/front-matter/) of a post or page, you can determine which template file your content should be rendered into. Template files should be placed in the `_layouts` folder in your project directory.

## Variables

A variable can be defined in your template using the following syntax:

<pre><code>&#123;&#123; title }}</code></pre>

This will render the title of the current post or page. The content of the variable depends on the current context, which is explained in more detail [here](/variables/).

## Tags

Stencil defines several tags that perform special tasks within your template.

### Include 

You can include other template files in your template using the `include` tag.

<pre><code class="handlebars">&#123;% include "header.html" %}</code></pre>

Spelt looks for these files inside your project's `_includes` directory.

### For

A for loop allows you to iterate over a collection of items. For instance, your `index.html` file might contain something similar to this:

<pre><code class="handlebars">&#123;% for post in posts %}
  &lt;h2>&lt;a href="&#123;{ post.url }}">&#123;{ post.title }}&lt;/a>&lt;/h2>
&#123;% endfor %}</code></pre>


### If 

If statements allow you conditionally render part of your template based on whether a variable is _truthy_ (evaluates to true). For example:

<pre><code class="handlebars">&#123;% if title %}
 &#123;{ title }}
&#123;% else %}
 &#123;{ site.title }}
&#123;% endif %}</code></pre>

Similarly you can check for equality using the `==` operator:

<pre><code class="handlebars">&#123;% if page.title == "About" %}
 // render something specific to About page
&#123;% endif %}</code></pre>

### Ifnot

The `ifnot` tag renders its contents when a variable is falsey (evaluates to false).

<pre><code class="handlebars">&#123;% ifnot post.category %}
 &lt;p>Category undefined&lt;/p>
&#123;% endif %}</code></pre>

### Gists and math typesetting

In addition to the standard Stencil tags, Spelt supports [embedding GitHub gists](/gists/) using the `gist` tag, and [math typesetting](/katex/) using the `katex` tag. 

## Filters

Filters allow you to transform the value of a variable in your template. For example:

{% raw %}
```handlebars
{{ title | uppercase }}
```
{% endraw %}

Spelt supports many different filters, see [this page](/filters/) for a complete reference.