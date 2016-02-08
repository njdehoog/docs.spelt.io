---
layout: post
title: Pagination
date: 2011-02-05 13:35:41 +0100
permalink: pagination
category: customization
---

It is common to split a list of blog posts up into multiple pages, which is called pagination. To enable pagination for your site, add the following line to your `_config.yml` file:

```yml
paginate: 5
```

This variable represents the number of items that should be displayed per page, so you can change this to suit your preferences.

When you have set this variable, the following variables will become available to your template files. Note that pagination is __only__ available for `index.html` files. However, this does not have to be your main `index.html`, it can also be in a subdirectory, e.g.: `blog/index.html`.

| Variable | Description |
| -------- | ----------- |
| `paginator.per_page` | Number of posts per page. |
| `paginator.page` | The number of the current page. |
| `paginator.total_pages` | The total number of pages. |
| `paginator.total_items` | The total number of items. |
| `paginator.multiple_pages` | Boolean value. True if `total_pages > 0`  |
| `paginator.next_page` | The number of the next page.  |
| `paginator.next_page_path` | The path to the next page. |
| `paginator.previous_page` | The number of the previous page.  |
| `paginator.previous_page_path` | The path to the previous page. |

## Sample index.html file

{% raw %}
```html 
---
layout: default
---

<!-- This loops through the paginated posts -->
{% for post in paginator.posts %}
  <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
  <p class="author">
    <span class="date">{{ post.date }}</span>
  </p>
{% endfor %}

<!-- Pagination links -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}" class="previous">Previous</a>
  {% else %}
    <span class="previous">Previous</span>
  {% endif %}
  <span class="page_number ">Page: {{ paginator.page }} of {{ paginator.total_pages }}</span>
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="next">Next</a>
  {% else %}
    <span class="next ">Next</span>
  {% endif %}
</div> 
```
{% endraw %}