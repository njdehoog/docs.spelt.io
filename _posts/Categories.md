---
layout: post
title: Categories
date: 2014-02-05 12:22:21 +0100
category: templates
permalink: categories
---

When creating your blog, you might want to organize your blog posts by assigning each of them to a category. To assign a post to a category you set the `category` variable in the front matter.

```
---
layout: post
title: The 10 best pets for a mission to Mars
category: space
---
```

A post can also belong to multiple categories. This can be specified by setting the `categories` (plural) variable to a [YAML list](http://en.wikipedia.org/wiki/YAML#Lists) or a comma-separated string, e.g.:

```
---
layout: post
title: The 10 best pets for a mission to Mars
categories: space, important-questions
---
```

## Templates

Defining a category will expose the name of that category as a variable to your template files. This variable contains a list of all blog posts assigned to that category. To render the titles of all blog posts in the _templates_ category, you could write the following:

{% raw %}
```
{% for post in site.categories.space %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
{% endfor %}
```
{% endraw %}
