## Styleguide Front-End

## Structure HTML
This structure was based on [Idiomatic HTML](https://github.com/necolas/idiomatic-html), [@mdo](http://mdo.github.io/code-guide/).

> * [Sintaxe](#sintaxe)
> * [Doctype](#doctype)
> * [Lang](#lang)
> * [Encoding of characters](#encoding-of-characters)
> * [IE compatibility mode](#ie-compatibility-mode)
> * [Inserting CSS and JavaScript](#inserting-css-and-javaScript)
> * [Lowercase](#lowercase)
> * [Order of attributes](#order-of-attributes)
> * [Boolean attributes](#boolean-attributes)
> * [Order loading](#order-loading)


## Sintaxe

* Always use double quotes, not single quotes.
* Never include a backslash in the unique elements (eg, `<img>` or `<hr>`)

## Doctype HTML5
Basic structure of a HTML5 markup

``` html
<!DOCTYPE html>
<html>
  <head>
  </head>
</html>
```

## Lang
You should specify the language of the documents. (eg, `pt-br` or `en`).

```html
<html lang="en">
</html>
```

## Encoding of characters
Use `UTF-8` the default encoding of HTML documents.

```html
<head>
  <meta charset="utf-8">
</head>
```

## IE compatibility mode
Internet Explorer supports the use of a document compatibility `<meta>` tag to specify what version of IE the page should be rendered. You should force edge mode.

```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

## Inserting CSS and JavaScript
According to the specifications of HTML5, there is no need to specify a type attribute when we include CSS and JavaScript files as `text/css` and `text/javascript`.

```html
<!-- Not -->
<link type="text/css" rel="stylesheet" href="style.css">
<script type="text/javascript" src="script.js"></script>

<!-- Yes -->
<link rel="stylesheet" href="style.css">
<script src="script.js"></script>
```

## Lowercase
Always use lowercase tag and attribute names.

```html
<!-- Not -->
<div class="navigationPrimary"></div>

<!-- Yes -->
<div class="navigation-primary"></div>
```

## Order of attributes
HTML attributes must use this standard order.

* `class`
* `id`
* `data-*`
* `for`, `type`, ou `href`
* `src`, `for`, `type`, `href`
* `title`, `alt`
* `method`, `action`
* `aria-*`, `role`

## Boolean attributes
If you need to include values in attributes, you need not follow this rule WhatWG:

> If the attribute is present, its value should be an empty string or [...] the canonical attribute name, without blanks.

```html
<input type="text" disabled>

<input type="checkbox" value="1" checked>

<select>
  <option value="1" selected>1</option>
</select>
````

## Order loading
How `javascript` is obstructive stopping the entire charging process until it is completely caregado, it is stated that it is loaded by last before the tag fachamento `</body>`.
With all exitem certain `javascript` to be loaded on top inside the `<head>` for some kind of dependence, in which case it should be placed after the `CSS` carregademento.


```html
<!DOCTYPE html>
<html>
  <head>
  </head>
  
  <body>
    <script src="script.js"></script>  
  </body>
</html>
```
or so if javascript needs to be loaded before all
```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
  </head>
  
  <body>  
  </body>
</html>
```
