---
layout: post
title: Markdown
date: 2016-01-29 12:41:26 +0100
category: writing
permalink: markdown
---

Spelt supports the [Markdown](http://daringfireball.net/projects/markdown/) format for writing your blog posts. Markdown syntax allows you to structure your text using a few simple characters. If you haven't used Markdown before, don't worry, it doesn't take more than a few minutes to understand the basics.

## Basics

To get you started, these are some basic examples of Markdown formatting (adapted from John Gruber's guide on [Markdown basics](http://daringfireball.net/projects/markdown/basics)).

### Paragraphs, headers and block quotes.

A paragraph is simply one or more consecutive lines of text, separated by one or more blank lines.

Headers are defined by putting 1 to 6 hash marks (#) at the beginning of a line — the number of hashes equals the resulting HTML header level.

Block quotes are indicated using email-style ‘>’ angle brackets.

Markdown:

```markdown
# A First Level Header
## A Second Level Header

Now is the time for all good men to come to
the aid of their country. This is just a
regular paragraph.

The quick brown fox jumped over the lazy
dog's back.

### Header 3

> This is a block quote.
> 
> This is the second paragraph in the block quote.
>
> ## This is an H2 in a block quote
```

Output:

---------------------------------------
A First Level Header
====================

A Second Level Header
---------------------

Now is the time for all good men to come to
the aid of their country. This is just a
regular paragraph.

The quick brown fox jumped over the lazy
dog's back.

### Header 3

> This is a block quote.
> 
> This is the second paragraph in the block quote.
>
> ## This is an H2 in a block quote

---------------------------------------

### Emphasis

Markdown uses asterisks and underscores to indicate emphasis.

Markdown:

```markdown
Some of these words *are emphasized*.
Some of these words _are emphasised also_.

Use two asterisks for **strong emphasis**.
Or, if you prefer, __use two underscores instead__.
```

Output:

---------------------------------------
Some of these words *are emphasized*.
Some of these words _are emphasised also_.

Use two asterisks for **strong emphasis**.
Or, if you prefer, __use two underscores instead__.

---------------------------------------

### Lists

Unordered (bulleted) lists use asterisks, pluses, and hyphens (*, +, and -) as list markers. These three markers can be used interchangeably.

Markdown:

```markdown
* Candy
* Gum
* Booze
	* Bourbon
	* Gin
```

Output:

---------------------------------------
* Candy
* Gum
* Booze
	* Bourbon
	* Gin

---------------------------------------

Ordered (numbered) lists use regular numbers, followed by periods, as list markers:

Markdown:

```markdown
1.  Red
2.  Green
3.  Blue
```

Output:

---------------------------------------
1.  Red
2.  Green
3.  Blue

---------------------------------------

### Links

Defining a link in Markdown in straightforward. The syntax is as follows:

```markdown
This is an [example link](http://example.com/).
```

Output:

---------------------------------------
This is an [example link](http://example.com/).

---------------------------------------

### Images

The syntax for embedding images is very similar to the syntax for defining links. It works as follows (title is optional):

```markdown
![alt text](https://media.giphy.com/media/xwtnF7qVyujQc/giphy.gif "Title")
```

Output:

---------------------------------------
![alt text](https://media.giphy.com/media/xwtnF7qVyujQc/giphy.gif "Title")

---------------------------------------

### <a name="code-snippets"></a>Code

Spelt supports both inline code spans:

```markdown
Why does nobody use the `<marquee>` tag anymore?
```

---------------------------------------
Why does nobody use the `<marquee>` tag anymore?


---------------------------------------

And [GitHub style](https://help.github.com/articles/creating-and-highlighting-code-blocks/) fenced code blocks:

    ```swift
    // Did you know Spelt is completely written in Swift?
    // It looks something like this:
    
    struct FooBar {
        var bar: Int = 0
    
        fun foo() {
            print("bar=\(bar)")
        }
    }
    ```

Which produces:

```swift
// Did you know Spelt is completely written in Swift?
// It looks something like this:

struct FooBar {
    var bar: Int = 0

    func foo() {
        print("bar=\(bar)")
    }
}
```

Notice that you can define which language your code is written in. If you don't define a language, the syntax highlighter will automatically try to detect the language for you.

Fenced code blocks and syntax highlighting are technically not part of Markdown. Syntax highlight for Spelt templates is implemented using [highlight.js](https://highlightjs.org/).

