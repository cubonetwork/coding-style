# Front-end 

> "Every line of code should appear to be written by a single person, no matter the number of contributors." - Chinese Proverb.

The following document describes the rules of writing in development languages that I use: HTML, CSS and JavaScript.

The idea of this repository is not to be a complete code guide. Only to have a place for myself and other developers who participate in my projects able to inform the coding standards used.

As this is a new document, some rules may not have been applied in old projects.

This is a live document and changes can occur at any time.

## Summary

1. [Commits](#commits)
1. [HTML](#html) 
1. [CSS](#css) 
1. [CSS Preprocessors](#css-preprocessors) 
1. [JavaScript](#js) 

<a name="commits"></a>
## 1. Commits

In order to facilitate the contribution by anyone in a project, all commit messages, pull request title or issues discussion must be in **English**.

Before commit adjusts in project, check if exists an open issue and make references for this issue using '#' in your commit message.

```javascript
// Good
git commit -m "Add placeholder on input #10"

// Bad
git commit -m "Add placeholder on input"
```

<a name="html"></a>
## 2. HTML

The main influence for the HTML rules is the [Code Guide by @mdo](https://github.com/mdo/code-guide).

### HTML Summary

1. [HTML Syntax](#html-syntax)
1. [HTML Comments](#html-comments)
1. [HTML Character Encoding](#html-encoding)
1. [HTML Attribute Order](#html-attribute-order)
1. [HTML Performance](#html-performance)
1. [HTML Base Code](#html-base)

<a name="html-syntax"></a>
### 2.1. HTML Syntax

Use soft tabs with two spaces. You can configure your editor for this.

```html
<!-- Good -->
<nav class="navbar">
  <ul class="nav">
    <li class="nav-item">
      <a class="nav-link">

<!-- Bad-->
<nav class="navbar">
      <ul class="nav">
            <li class="nav-item">
                  <a class="nav-link">
```

Always use double quotes.

```html
<!-- Good -->
<main class="main">

<!-- Bad-->
<div class='main'>
```

Don't include a `/` in self-closing elements.

```html
<!-- Good -->
<hr>

<!-- Bad-->
<hr />
```

Separate block element by a blank line and agroup the inners block elements.

```html
<!-- Good -->
<ul class="nav-tabs">
  <li>...</li>
  <li>...</li>
  <li>...</li>
  <li>...</li>
</ul>

<div class="tab-content">
  ...
</div>

<!-- Bad-->
<ul class="nav-tabs">

  <li>...</li>

  <li>...</li>

  <li>...</li>

  <li>...</li>

</ul>
<div class="tab-content">
  ...
</div>
```

<a name="html-comments"></a>
### 2.2. HTML Comments

Follow this rule to add comments in HTML.

```html
<!-- This is a good example -->
<!-- /Closing a good example -->
```

<a name="html-encoding"></a>
### 2.3. HTML Character Encoding

Always use UTF-8 for character encoding.

```html
<head>
  <meta charset="UTF-8">
</head>
```

<a name="html-attribute-order"></a>
### 2.4. HTML Attribute Order

HTML attributes should be in this order for facilitate the reading.

1. `class`
1. `id`, `name`
1. `data-*`
1. `src`, `for`, `type`, `href`
1. `title`, `alt`
1. `aria-*`, `role`

```html
<a class="..." id="..." data-modal="#overlay" href="#">

<input class="form-control" type="text">

<img class="img-rounded" src="..." alt="...">
```

<a name="html-performance"></a>
### 2.5. HTML Performance

No need to specify a type when including CSS and JavaScript files as `text/css` and `text/JavaScript`.

```html
<!-- Good -->
<link rel="stylesheet" href="assets/css/style.css">
<script src="scripts.min.js"></script>

<!-- Bad -->
<link rel="stylesheet" href="assets/css/style.css" type="text/css">
<script src="scripts.min.js" type="text/JavaScript"></script>
</head>
<body>
```

For a better performance, all JavaScripts files must be at the end of the code. Before closing the `<body>`.

```html
<!-- Good -->
<script src="scripts.min.js"></script>
</body>

<!-- Bad -->
<script src="scripts.min.js"></script>
</head>
<body>
```

Always minify the code in projects only in HTML. Task builders like [Grunt](http://gruntjs.com/) leaves this easier.

```html
<!-- Good -->
<html><head>...</head><body><div class="container">...</div></body></html>

<!-- Bad -->
<html>
  <head>
    ...
  </head>
  <body>
    <div class="container">
      ...
    </div>
  </body>
</html>
``` 
 
<a name="css"></a>
## 3. CSS

The main influences for the CSS rules are [Code Guide by @mdo](https://github.com/mdo/code-guide) and [idiomatic CSS](https://github.com/necolas/idiomatic-css/).

### CSS Summary

1. [CSS Syntax](#css-syntax)
1. [CSS Declaration Order](#css-order)
1. [CSS Class Name](#css-class-name)
1. [CSS Performance](#css-performance)
1. [CSS Media Queries](#css-media-queries) 

<a name="css-syntax"></a>
### 4.1. CSS Syntax

Use soft tabs with two spaces. You can configure your editor for this.

```css
/* Good */
.nav-item {
  display: inline-block;
  margin: 0 5px;
}

/* Bad */
.nav-item {
    display: inline-block;
    margin: 0 5px;
}
```

Always use double quotes.

```css
/* Good */
[type="text"]
[class^="..."]

.nav-item:after {
  content: "";
}

/* Bad */
[type='text']
[class^='...']

.nav-item:after {
  content: '';
}
```

Include a single space before the opening bracket of a ruleset.

```css
/* Good */
.header {
  ...
}

/* Bad */
.header{
  ...
}
```

Include a single space after the colon of a declaration.

```css
/* Good */
.header {
  margin-bottom: 20px;
}

/* Bad */
.header{
  margin-bottom:20px;
}
```

Include a semi-colon at the end of the last declaration in a declaration block.

```css
/* Good */
.header {
  margin-bottom: 20px;
}

/* Bad */
.header{
  margin-bottom:20px
}
```

Keep one declaration per line.

```css
/* Good */
.selector-1,
.selector-2,
.selector-3 {
  ...
}

/* Bad */
.selector-1, .selector-2, .selector-3 {
  ...
}
```

Single declarations should remain in one line.

```css
/* Good */
.selector-1 { width: 50%; }

/* Bad */
.selector-1 {
  width: 50%;
}
```

Separate each ruleset by a blank line.

```css
/* Good */
.selector-1 {
  ...
}

.selector-2 {
  ...
}

/* Bad */
.selector-1 {
  ...
}
.selector-2 {
  ...
}
```

Use lowercase, shorthand hex values and avoid specifying units is zero-values.

```css
/* Good */
.selector-1 {
  color: #aaa;
  margin: 0;
}

/* Bad */
.selector-1 {
  color: #AAAAAA;
  margin: 0px;
}
```

<a name="css-order"></a>
### 4.2. CSS Declaration Order

The declarations should be added in alphabetical order.

```css
/* Good */
.selector-1 {
  background: #fff;
  border: #333 solid 1px;
  color: #333;
  display: block;
  height: 200px;
  margin: 5px;
  padding: 5px;
  width: 200px;
}

/* Bad */
.selector-1 {
  padding: 5px;
  height: 200px;
  background: #fff;
  margin: 5px;
  width: 200px;
  color: #333;
  border: #333 solid 1px;
  display: block;
}
```

<a name="css-class-name"></a>
### 4.3. CSS Class Name

Keep class lowercase and use dashes to separate the classname.

```css
/* Good */
.page-header { ... }

/* Bad */
.pageHeader { ... }
.page_header { ... }
```

Use single dash to element name, double underline to element block and double dash to style modification.

```css
/* Good */
.page-header__action { ... }
.page-header__action__title { ... }
.page-header--active { ... }

.btn { ... }
.btn--primary { ... }

/* Bad */
.page-header-action { ... }
.page-header-action-title { ... }
.page-header-active { ... }

.btn { ... }
.btn-primary { ... }
```

Dashes and underline serve as natural breaks in related class. Prefix class based on the closest parent or base class.

```css
/* Good */ 
.nav { ... }
.nav__item { ... }
.nav__link { ... }

/* Bad */
.item-nav { ... }
.link-nav { ... }
```

Avoid giving too short names for class and always choose meaningful names that provide the class function.

```css
/* Good */
.btn { ... }
.page-header { ... }
.progress-bar { ... }

/* Bad */
.s { ... }
.ph { ... }
.block { ... }
```

<a name="css-performance"></a>
### 4.4. CSS Performance

Never use IDs.

```css
/* Good */
.header { ... }
.section { ... }

/* Bad */
#header { ... }
#section { ... }
```

Do not use selectors standards for not generic rules, always preferably for class.

```css
/* Good */
.form-control { ... }
.header { ... }
.section { ... }

/* Bad */
input[type="text"] { ... }
header
section
```

Avoid nesting elements, the preference is always to use class.

```css
/* Good */
.navbar { ... }
.nav { ... }
.nav__item { ... }
.nav__link { ... }

/* Bad */
.navbar ul { ... }
.navbar ul li { ... }
.navbar ul li a { ... }
```

Nest only when need change the class comportament with interference for other class. Keep the nested on max of three elements.

```css
/* Good */
.modal-footer .btn { ... }
.progress.active .progress-bar { ... }

/* Bad */
.modal-btn { ... }
.progress.active .progress-bar .progress-item span { ... }
```

Always minify the CSS code. Task builders like [Grunt](http://gruntjs.com/) leaves this easier.

```css
<!-- Good -->
.navbar { ... }.nav { ... }.nav-item { ... }.nav-link { ... }

<!-- Bad -->
.nav-item {
  ...
}
.nav-link {
  ...
}
```

<a name="css-media-queries"></a>
### 4.5 CSS Media Queries

Start the development with generic rules with and add media queries with mobile first.

```css
/* Good */
.navbar {
  margin-bottom: 20px;
}

@media (min-width: 480px) {
  .navbar {
    padding: 10px;
  }
}

@media (min-width: 768px) {
  .navbar {
    position: absolute;
    top: 0;
    left: 0;
  }
}

@media (min-width: 992px) {
  .navbar {
    position: fixed;
  }
}

/* Bad */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
}

@media (max-width: 767px) {
  .navbar {
    position: static;
    padding: 10px;
  }
}

```

Keep the media queries as close to their relevant rule sets whenever possible. Don't bundle them all in a separate stylesheet or at the end of the document.

```css
.navbar { ... }
.nav { ... }
.nav-item { ... }

@media (min-width: 480px) {
  .navbar { ... }
  .nav { ... }
  .nav-item { ... }
}
```

<a name="css-preprocessors"></a>
## 4. CSS Preprocessors

I use pre-processors in all projects. Today I use **Stylus**, but some projects use `LESS`.

### CSS Preprocessors Summary

1. [CSS Preprocessors Syntax](#preprocessors-syntax)  
1. [CSS Preprocessors Performance](#preprocessors-performance) 
1. [CSS Preprocessors Media Queries](#preprocessors-media-queries) 
1. [CSS Preprocessors Comments](#preprocessors-comments)


<a name="preprocessors-syntax"></a>
### 5.1. CSS Preprocessors Syntax

Use soft tabs with two spaces. You can configure your editor for this.

```css
// Good
.nav-item 
  display inline-block  

// Bad
.nav-item 
    display inline-block  
```

Do not use semi-colons, commas or brackets

```css
// Good
.header 
  position fixed
  top 0
  right 0
  left 0

// Bad
.header {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
}
``` 

Keep one declaration per line.

```css
// Good
.selector-1,
.selector-2,
.selector-3 
  ...
 

// Bad
.selector-1, .selector-2, .selector-3 
  ... 
``` 

Separate nested ruleset by a blank line and blocks ruleset by a double blank line.

```css
// Good
.navbar 
  margin 0 0 20px

  li 
    display inline-block


.nav 
  display block

  li 
    float left


// Bad
.navbar 
  margin 0 0 20px 
  li 
    display inline-block 
.nav 
  display block 
  li 
    float left
``` 

Use **$** for the variables.

```css
// Good
$gray-darker  = #111
$gray-dark    = #393C45
$gray         = #555
$gray-light   = #aaa
$gray-lighter = #ECF1F5
$gray-white   = #fbfbfb
```

<a name="preprocessors-performance"></a>
### 5.2. CSS Preprocessors Performance

Warning with nesting rules of preprocessors. Continue keep without nesting.

```css
// Good
.nav-item 
  ...

// Bad
.navbar 
  .nav 
    .nav-item 
      ... 
```

**Do not use @extends**, [always use mixins](http://csswizardry.com/2016/02/mixins-better-for-performance/).

```css
reset(arg = '')
  
  if (arg == list) 
    margin 0
    padding-left 0
    list-style none
    
  if (arg == form)  
    background 0
    border 0
    padding 0

.nav
  reset(list)

.btn
  reset(form)
```
 
<a name="preprocessors-media-queries"></a>
### 5.3. CSS Preprocessors Media Queries

Provide the media queries rules inside the element.

```css 
.navbar 
  position absolute
  top 5px
  z-index 5
   
  @media (min-width $screen-sm) 
    position fixed
    margin-right $space-sm
  
  @media (min-width $screen-md)  
    right 0 
    top 10px 
```
 
<a name="preprocessors-comments"></a>
### 5.4. CSS Preprocessors Comments

Provide one summary on header of files.

```css 
//  
// Variables
//
// 1. Colors
// 2. Spaces 
// 3. Media Queries 
// 4. Typography
//
// ==================================================

// 
// 1. Colors
// --------------------------------------------------

...

// 
// 2. Spaces
// --------------------------------------------------

...
```

For main element. 

```css  
// 
// 1. Header
// -------------------------------------------------- 
... 
```

For children elements. 

```css   
// 1.1 Header Item
// -------------------------------------------------- 
...
```

For generic comments

```css   
// Simple comment

// Block
// Comment
...
``` 

<a name="js"></a>
## 5. JavaScript

The main influences for the JavaScript rules are [idiomatic.js](https://github.com/rwldrn/idiomatic.js/) and [Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style/).

### JavaScript Summary

1. [JavaScript Syntax](#js-syntax)
1. [JavaScript Variables](#js-variables)
1. [JavaScript Performance](#js-performance)
1. [JavaScript and HTML5 Data Attributes](#js-data-attributes)
1. [JavaScript Comments](#js-comments)

<a name="js-syntax"></a>
### 6.1. JavaScript Syntax

Use soft tabs with two spaces. You can configure your editor for this.

```js
// Good
while (condition) {
  statements
}

// Bad
while (condition) {
    statements
}
```

Always use semicolons.

```js
// Good
var me = $(this);
test();

// Bad
var me = $(this)
test()
```

Always use single quotes.

```js
// Good
var string = '<p class="foo">Lorem Ipsum</p>';
var noteClick = me.attr('data-note');

// Bad
var string = "<p class='foo'>Lorem Ipsum</p>";
var noteClick = me.attr("data-note");
```

Keep `else` in the same line of closure of the `if`.

```js
// Good
if ( true ) {
  ...
} else {
  ...
}

// Bad
if ( true ) {
  ...
}
else {
  ...
}
```

Add spaces between operators.

```js
// Good
for (i = 0; i < 10; i++) {
  ...
}

// Bad
for (i=0;i<10;i++) {
  ...
}
```

Never add a space between the keyword function and the function name.

```js
// Good
foo(function() {
  ...
});

// Bad
foo ( function () {
  ...
});
```

Add spaces outside parentheses `()` but avoid it inside.

```js
// Good
if (condition) {
  statement
}

// Bad
if( condition ){
  statement
}
```

For conditionals always use curly brackets `{}`.

```js
// Good
if (condition) {
  statement
} else if (condition) {
  statement
} else {
  statement
}

// Bad
if (condition) statement;
else if (condition) statement;
else statement;
```

For strict equality checks `===` should be used in favor of `==`.

```js
// Good
if (foo === 'foo') {
  statement
}

// Bad
if (foo == 'foo') {
  statement
}
```

<a name="js-variables"></a>
### 6.2. JavaScript Variables

All variables should be declared before used.

```js
// Good
var me = $(this);
var noteClick = me.attr('data-note');
notes[noteClick].play();

// Bad
notes[noteClick].play();
var me = $(this);
var noteClick = me.attr('data-note');
```

Always use `var` to declare variables.

```js
// Good
var me = $(this);

// Bad
me = $(this);
```

<a name="js-performance"></a>
### 6.3. JavaScript Performance

Use [JSHint](http://www.jshint.com/) to detect errors and potential problems.

Always minify and concat the JavaScript code. Task builders like [Grunt](http://gruntjs.com/) leaves this easier.

<a name="js-data-attributes"></a>
### 6.4. JavaScript and HTML5 Data Attributes

Avoid using classes to start in a JavaScript interaction. To do so, use ***HTML5 Data Attributes***.

```js
// Good
$('[data-component="tab"]');

// Bad
$('.tab');
```

This approach makes the classes are only responsible for styling.

Thus elements that share the same style, but do not have the same interaction, may function separately.
