---
layout: post
title: Filters
date: 2016-01-29 13:41:45 +0100
category: templates
permalink: filters
---

Filters allow you to transform the value of a variable in your template. For example:

{% raw %}
```handlebars
{{ title | uppercase }}
```
{% endraw %}

Or:

{% raw %}
```handlebars
{{ url | prepend: site.url }}
```
{% endraw %}

## Date filters

| Description | Filter and output |
| ------------- | :-------------: |
| __Date__<br />Convert a date to its string representation using [specified format](http://waracle.net/iphone-nsdateformatter-date-formatting-table/). | <code>&#123;{ date \| date: "EEE, MMM dd yyyy HH:mm"  }}</code><br/><code class="output">Fri, Jan 29 2016 13:42</code> |
| __Date to string__<br />Convert a date to its default string representation using your system's localization settings. | <code>&#123;{ date \| date_to_string  }}</code><br/>e.g.: <code class="output">29 January 2016</code> |
| __Date to RFC-822__<br />Convert a date into the RFC-822 format used for RSS feeds. | <code>&#123;{ date \| date_to_rfc822  }}</code><br/><code class="output">Fri, 29 Jan 2016 13:42:45 +0100</code> |
| __Date to XML Schema__<br />Convert a Date into XML Schema (ISO 8601) format. | <code>&#123;{ date \| date_to_xmlschema  }}</code><br/><code class="output">2016-01-29T13:42:45+01:00</code> |


## String filters

| Description | Filter and output |
| ------------- | :-------------: |
| __Lowercase__<br/>Convert a string to lowercase text. | <code>&#123;{ "Spelt" \| lowercase }}</code><br/><code class="output">spelt</code> |
| __Uppercase__<br/>Convert a string to uppercase text. | <code>&#123;{ "spelt" \| uppercase }}</code><br/><code class="output">SPELT</code> |
| __Capitalize__<br/>Capitalize each word in a string. | <code>&#123;{ "some sentence" \| capitalize  }}</code><br/><code class="output">Some Sentence</code> |
| __Markdownify__<br />Convert a Markdown-formatted string into HTML. | <code>&#123;{ "# Title" \| markdownify  }}</code><br/><code class="output">&lt;h1>Title&lt;/h1></code> |
| __XML Escape__<br />Escape some text for use in XML. | <code>&#123;{ "this&that" \| xml_escape  }}</code><br/><div class="output">`this&amp;that`</div> |
| __URL Encode__<br />Convert string for use in URLs by percent-encoding disallowed characters. | <code>&#123;{ "some string" \| url_encode  }}</code><br/><code class="output">some%20string</code> |
| __Prepend__<br />Prepend characters to a string. | <code>&#123;{ ", World!" \| prepend: "Hello"  }}</code><br/><code class="output">Hello, World!</code> |
| __Append__<br />Append characters to a string. | <code>&#123;{ "Hello" \| prepend: ", World!"  }}</code><br/><code class="output">Hello, World!</code> |
| __Replace__<br />Replace all occurrences of a string with specified replacement. | <code>&#123;{"Hey there!"\|replace:"there","you"}}</code><br/><code class="output">Hey you!</code> |
| __Strip HTML__<br />Strip all HTML tags from a string. | <code>&#123;{"&lt;h1>Hello&lt;/h1>, World!" \| strip_html}}</code><br/><code class="output">Hello, World!</code> |
| __Strip newlines__<br />Remove line breaks/newlines from a string. | <code>&#123;{ post.excerpt \| strip_newlines }}</code> |
| __Truncate__<br />Truncate a string to specified number of characters. | <code>&#123;{"It's raining cats and dogs"\|truncate:17}}</code><br/><code class="output">It's raining cats</code> |
| __Number of words__<br />Count the number of words in some text. | {% raw %}`{{content | strip_html | number_of_words}}`{% endraw %}<br/><code class="output">42</code> |


## Array filters
| Description | Filter and output |
| ------------- | :-------------: |
| __Join__<br />Join the elements of an array with the specified character.  | {% raw %}`{{ categories | join: ", " }}`{% endraw %}<br/><code class="output">static site generators, documentation</code> |
| __Array to sentence__<br />Convert an array into a sentence. Useful for listing tags.  | {% raw %}`{{ tags | array_to_sentence_string }}`{% endraw %}<br/><code class="output">foo, bar, and baz</code> |

## Math filters

| Description | Filter and output |
| ------------- | :-------------: |
| __Divide by__<br />Divides an output by a number.  | {% raw %}`{{ 100 | divided_by: 10 }}`{% endraw %}<br/><code class="output">10.0</code> |
| __Ceil__<br />Rounds an output up to the nearest integer. | {% raw %}`{{ 4.3 | ceil }}`{% endraw %}<br/><code class="output">5</code> |
| __Floor__<br />Rounds an output down to the nearest integer. | {% raw %}`{{ 4.9 | floor }}`{% endraw %}<br/><code class="output">4</code> |