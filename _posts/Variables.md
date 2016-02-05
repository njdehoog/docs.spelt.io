---
layout: post
title: Variables
date: 2015-01-29 13:19:21 +0100
category: customization
permalink: variables
---

In addition to the variables defined in a file's [front matter](/front-matter/), Spelt exposes a set of variables for you to use in your template files.

| Variable | Description |
| -------- | ----------- |
| `site` | Variables from `_config.yml` are exposed as properties of `site`, e.g.: `site.title`. |
| `content(s)` | In layout files, this contains the content of the current post or page. |
| `posts` | A reverse chronological list of all blog posts. |
| `paginator` | When `paginate` is defined in the configuration file, this variable becomes available. See [pagination](/pagination/) for details. |

## Site variables

| Variable | Description |
| -------- | ----------- |
| `site.time` | The current time/date (when the site is being generated). |

## Paginator variables

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

