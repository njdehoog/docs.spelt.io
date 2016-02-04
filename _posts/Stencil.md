---
layout: post
title: Layouts
date: 2016-01-29 13:42:45 +0100
category: customization
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

## Filters

Filters allow you to transform the value of a variable in your template. For example:

<pre><code class="handlebars">&#123;{ title | uppercase }}</code></pre>

Or:

<pre><code class="handlebars">&#123;{ url | prepend: site.url }}</code></pre>

Spelt currently supports the following filters:

| Description | Filter and output |
| ------------- | :-------------: |
| __Lowercase__<br/>Convert a string to lowercase text. | <code>&#123;{ "Spelt" \| lowercase }}</code><br/><code class="output">spelt</code> |
| __Uppercase__<br/>Convert a string to uppercase text. | <code>&#123;{ "spelt" \| uppercase }}</code><br/><code class="output">SPELT</code> |
| __Capitalize__<br/>Capitalize each word in a string. | <code>&#123;{ "some sentence" \| capitalize  }}</code><br/><code class="output">Some Sentence</code> |
| __Date__<br />Convert a date to its string representation using [specified format](http://waracle.net/iphone-nsdateformatter-date-formatting-table/). | <code>&#123;{ date \| date: "EEE, MMM dd yyyy HH:mm"  }}</code><br/><code class="output">Fri, Jan 29 2016 13:42</code> |
| __Date to string__<br />Convert a date to its default string representation using your system's localization settings. | <code>&#123;{ date \| date_to_string  }}</code><br/>e.g.: <code class="output">29 January 2016</code> |
| __Date to RFC-822__<br />Convert a date into the RFC-822 format used for RSS feeds. | <code>&#123;{ date \| date_to_rfc822  }}</code><br/><code class="output">Fri, 29 Jan 2016 13:42:45 +0100</code> |
| __Date to XML Schema__<br />Convert a Date into XML Schema (ISO 8601) format. | <code>&#123;{ date \| date_to_xmlschema  }}</code><br/><code class="output">2016-01-29T13:42:45+01:00</code> |
| __Markdownify__<br />Convert a Markdown-formatted string into HTML. | <code>&#123;{ "# Title" \| markdownify  }}</code><br/><code class="output">&lt;h1>Title&lt;/h1></code> |
| __XML Escape__<br />Escape some text for use in XML. | <code>&#123;{ "this&that" \| xml_escape  }}</code><br/><div class="output">`this&amp;that`</div> |
| __URL Encode__<br />Convert string for use in URLs by percent-encoding disallowed characters. | <code>&#123;{ "some string" \| url_encode  }}</code><br/><code class="output">some%20string</code> |
| __Prepend__<br />Prepends characters to a string. | <code>&#123;{ ", World!" \| prepend: "Hello"  }}</code><br/><code class="output">Hello, World!</code> |
| __Append__<br />Appends characters to a string. | <code>&#123;{ "Hello" \| prepend: ", World!"  }}</code><br/><code class="output">Hello, World!</code> |
| __Replace__<br />Replaces all occurrences of a string with specified replacement. | <code>&#123;{ "Hey there!"\|replace:"there","you" }}</code><br/><code class="output">Hey you!</code> |
