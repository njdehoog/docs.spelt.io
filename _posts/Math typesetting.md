---
layout: post
title: Math typesetting
date: 2012-02-05 11:11:28 +0100
permalink: katex
category: writing
---

Spelt integrates with [KaTeX](https://github.com/Khan/KaTeX) to render math expressions. Equations such as {% katex inline:true %}S_n = a \times \frac{1-r^n}{1-r}{% endkatex %}
 can be displayed inline.

Alternatively, they can be shown on a new line:

{% katex %}
f(x) = \int \frac{2x^2+4x+6}{x-2}
{% endkatex %}


## Usage

To enable [KaTeX](https://github.com/Khan/KaTeX) math rendering for your theme, make sure to include the following in the `<head>` section of your HTML.

```
<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/KaTeX/0.5.1/katex.min.css">
<script src="//cdnjs.cloudflare.com/ajax/libs/KaTeX/0.5.1/katex.min.js"></script>
```

Additionally, paste the following script in a file called `katex_init.js`:

```js
var elements = document.getElementsByTagName('script')

Array.prototype.forEach.call(elements, function(element) {
  if (element.type.indexOf('math/tex') != -1) {
     // Extract math markdown
     var textToRender = element.innerText || element.textContent;

     // Create span for KaTeX
     var katexElement = document.createElement('span');

     // Support inline and display math
     if (element.type.indexOf('mode=display') != -1){
       katexElement.className += "math-display";
       textToRender = '\\displaystyle {' + textToRender + '}';
     } else {
       katexElement.className += "math-inline";
     }

     katex.render(textToRender, katexElement);
     element.parentNode.insertBefore(katexElement, element);
  }
});
```

And insert this line right before the closing `</body>` tag: 

```
<script src="/js/katex_init.js"></script>
```

> This snippet assumes that you have placed the `katex_init.js` file in a folder called `js` at the root of your project directory. Make sure the path points to where you store Javascript files for your theme.
