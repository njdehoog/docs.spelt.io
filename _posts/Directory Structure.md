---
layout: post
title: Directory structure
category: getting-started
permalink: directory-structure
date: 2013-02-01
---

When creating a new project, Spelt creates a folder structure similar to the one below. The structure of your project folder is important. It ensures that Spelt knows where to look for which type of files when generating your site. Spelt will help you maintain this structure, for instance, when creating a blog post from the app, it will automatically be placed in the `_posts` directory.

```text
.
├── _config.yml
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── Sample Post.md
|   └── Markdown and HTML.md
├── _build
├── _sass
└── index.html
```

| File/Directory | Description |
| ------------- | ------------- |
| `_config.yml`  | Stores configuration variables for your site. |
| `_includes` | Contains partial template files that can be included in templates using the following syntax: <br><code>&#123;% include "header.html" %}</code>  |
| `_layouts`  | These are the main template files. Files can be configured to be rendered into a template by setting the `layout` parameter in its [front matter](/front-matter/). |
| `_posts` | The directory that contains your blog posts. |
| `_build` | This is where Spelt puts your generated site when previewing or publishing. |
| `_sass` | Sass includes directory. This is where you should put your sass partials if you use them. |
| `index.html` | Provides the starting point for your blog. Will be processed by Spelt provided that it contains [front matter](/front-matter/). |
| Other files/folders | Other files and folders will be copied verbatim to the generated site, unless a file contains [front matter](/front-matter/), in which case it will be processed by the rendering engine. |