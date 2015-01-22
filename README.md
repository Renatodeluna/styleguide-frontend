#![logo](logo.png)

## Introduction

Welcome, this is a Style Guide for Front-End. A series of recommendations on how to write your CSS, HTML and Javascript code, based on architectures like SMACSS, BEM, SUIT, @mdo, Idiomatic CSS/HTML/JS.

Ensuring that all participants in the development of a project to work with the same Code base and using the same terminology: <b>Developing a standard design, fast and lasting results.</b>

## Concept

* Block and Elements of the [BEM](http://bem.info/)
* Categorizations and States of the [SMACSS](http://smacss.com/)
* Modifiers of the [SUIT CSS](https://suitcss.github.io/)
* Architecture and Standards of [@mdo](http://mdo.github.io/code-guide/), [Idiomatic CSS](https://github.com/necolas/idiomatic-css), [idiomatic HTML](https://github.com/necolas/idiomatic-html) and [idiomatic JS](https://github.com/necolas/idiomatic-js)

## Benefits

* <b>Facilitate the maintenance of long-term projects;</b>
* <b>Code understanding facility;</b>
* <b>Scalable code;</b>
* <b>Standard designs;</b>
* <b>Code reuse;</b>
* <b>Reduce the learning curve for new team members;</b>
* <b>Modularization design;</b>

## Styleguide Front-End

* <big>**[CSS Styleguide](/css.md)**</big> 
* <big>**[HTML Styleguide](/html.md)**</big>
* <big>**[Javascript Styleguide](/javascript.md)**</big> 

## Nomenclature Stylesheet
The pre-porcessador SASS was adopted, but it is your choice to use what is most convenient for your project, the Styleguide Front End will be useful to everyone.

1 - Utilization hyphen to separate words in large or compound names:
```scss

  .menu-bar {}

```

2 - Use underscores to separate a block of an element:
```scss

  .menu_item {}

```

3 - Use double hyphen to structure modifiers:
```scss

  .button--big {}

```

4 - Use the 'is-' prefix to indicate the state of that element:
```scss

  .is-active {}

```
* More details of these nomenclature [CSS Styleguide](/css.md).

## Structure file

```
  app
  ├── assets
  |   ├── fonts
  |   |
  |   ├── img
  |   |   ├── public
  |   |   └── sprites
  |   |       ├── default
  |   |       └── retina
  |   |
  |   ├── js
  |   |   ├── modules
  |   |   └── vendor
  |   |       └── jquery
  |   |
  |   ├── sass
  |	  |   ├── base
  |	  |   |   ├── _reset.scss
  |	  |   |   ├── _typography.scss  
  |	  |   |   ├── _fonts.scss
  |	  |   |   └── _grid.scss
  |	  |   |
  |	  │   ├── modules
  |	  |   |   ├── _buttons.scss
  |	  |   |   ├── _dropdown.scss
  |	  |   |   ├── _gallery.scss
  |	  |   |   └── _modal.scss
  |	  |   |
  |	  │   ├── layouts
  |   |   |   ├── _header.scss
  |   |   |   ├── _main.scss
  |   |   |   ├── _footer.scss
  |   |   |   └── pages
  |   |   |       ├── _home.scss
  |   |   |       └── _about.scss
  |   |   |
  |	  │   ├── helpers
  |	  |   |   ├── _class.scss
  |	  |   |   ├── _functions.scss
  |	  |   |   ├── _mixins.scss
  |	  |   |   ├── _placeholder.scss
  |	  |   |   └── _variables.scss
  |	  |   |
  |	  |   ├── breakpoints
  |	  |   |   ├── _mobile.scss
  |	  |   |   ├── _tablets.scss
  |	  |   |   └── _desktop.scss
  |	  |   |
  |	  │   ├── style.scss
  |	  |   └── style-ie.scss
  |	  |
  |	  └── css
  |	      |── style.css
  |	      └── style-ie.css
  |
  └── index.html
  
```

## EditorConfig

Set your editor with the following settings to avoid common inconsistencies in the code dirty and diffs:

* Use soft-tabs with 2 spaces
* Delete the blanks to save
* Set the encoding to UTF-8
* Place a new line at the end of files

Consider document and apply these settings for your project with [EditorConfig](http://editorconfig.org).

## Licença

[MIT License](http://opensource.org/licenses/MIT). © Copyright 2015, @renatodeluna.


