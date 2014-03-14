html-style-guide
================

MercadoLibre HTML Style Guide

## Anchors

### Description
* Defines an anchor and can be used as a link to another document, such as a marker, or both.


### Attibutes
<a href="#href">`href`</a>
<a href="#title">`title`</a>
<a href="#id">`id`</a>
<a href="#name">`name`</a>
<a href="#class">`class`</a>
<a href="#target">`target`</a>
<a href="#type">`type`</a>
<a href="#rel">`rel`</a>


### Basic implement
Specific `href` and `title` attributes
```html
<a href="https://github.com/mercadolibre/html-style-guide" title="Go to html style guide" >html-style-guide</a>
```

### Implement data attributes
```html
<a href="http://url.original" data-some-data="sting-data" title="link with data attr"></a>
```

### Good Practices
Anchors don't have auto close tag
```html
<!-- DON'T -->
<a href="url" title="title-text" />
```

```html
<!-- DO -->
<a href="url" title="title-text"></a>
```

<a name="title"></a>
Always specific a title attribute
```html
<!-- DON'T -->
<a href="url"></a>
```

```html
<!-- DO -->
<a href="url" title=""></a>
```

Never use other element if you want link any info
```html
<!-- DON'T -->
<span id="link" onclick="window.open('url')" ></span>
```

```html
<!-- DO -->
<a href="url" title="title-link" target="_blank"></a>
```

Always define a url and prevent it from javascript
```html
<!-- DON'T -->
<a href="javscript:void();" ></a>
```

```html
<!-- DO -->
<a href="http://www.url.bla" title="title-link"></a>
and prevent event on click this
```

<a name="id"></a>
Link info inside our content example
```html
<a href="#idReference" title="Go to Reference">Go to Reference</a>
(...our html content...)
<section id="idReference"></section>
```
Or
<a name="name"></a>
```html
<a href="#nameReference" title="Go to Reference">Go to Reference</a>
(...our html content...)
<a name="nameReference"></a>
<section id="reference"></section>
```


### Attibutes desription

#### Target
<span id="target"></span>

######Possible values

* `_blank` - *Open linked document in new windows or tab*
* `_self` - *It's a default, open linked document in the same context*
* `_parent` - *Open linked document in the parent frame*
* `_top` - *Open linked document in the top level of current context frame*



#### Bibliografía
http://www.htmlquick.com/es/reference/tags/a.html
http://www.htmlquick.com/es/reference/mime-types.html
http://www.htmlquick.com/es/reference/types.html#frame-target
http://stackoverflow.com/questions/11009597/correct-implementation-of-anchor-tag
http://line25.com/articles/10-html-tag-crimes-you-really-shouldnt-commit
http://stackoverflow.com/questions/134845/href-attribute-for-javascript-links-or-javascriptvoid0
http://moz.com/learn/seo/anchor-text
http://www.w3.org/TR/html4/types.html#h-6.16
http://stackoverflow.com/questions/4964130/target-blank-vs-target-new
http://www.w3.org/html/wg/drafts/html/master/Overview.html