---
layout: post
title: Front matter
date: 2016-01-25 17:45:22 +0100
category: writing
---

Spelt uses front matter to determine how it should render your files. Any file that contains front matter will be processed by the rendering engine. The front matter must start on the first line of a file, is defined by a set of triple-dashed lines, like in this example:

```yaml
---
layout: post
title:  Blogging Like a Hacker for Non-Hackers
date: 2015-09-10 09:41:00 +0100
---
```

In between those dashed lines you can specify metadata for your file. A blog post requires `title` and `date` to be define at the least.

The format used to specify this metadata is called [YAML](https://en.wikipedia.org/wiki/YAML). YAML is a human friendly way to represent some data. Any metadata that you specify here will be available to your template files.

## Predefined variables

There are a number of predefined variables that you can set in the front matter of your files.

| Variable | Description |
| ------------- | ------------- |
| `title`  | The title of your blog post or page.  |
| `date` | The date of the post. Dates must be specified in the format `YYYY-MM-DD HH:MM:SS +/-TTTT`. Hours, minutes, seconds, and timezone offset are optional.  |
| `layout`  | If defined, this specifies which layout to use. Layout files must be placed in the `_layouts` directory.  |
| `category`<br/>`categories` | You can specify one or more categories a blog post belongs to. Categories (plural) can be specified as a [YAML list](http://en.wikipedia.org/wiki/YAML#Lists) or a comma-separated string. |