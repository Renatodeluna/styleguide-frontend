## Styleguide Front-End

## Structure CSS
This structure was based on [Idiomatic CSS](https://github.com/necolas/idiomatic-css), [@mdo](http://mdo.github.io/code-guide/), [BEM](http://bem.info/), [SMACSS](http://smacss.com/), [SUIT CSS](https://suitcss.github.io/).

> * [Introduction](#introduction)
> * [Syntaxe](#syntaxe)
> * [Indenting](#indenting)
> * [Comments](#comments)
> * [Declarations](#declarations)
> * [Order of declarations](#order-of-declarations)
> * [Summarized properties](#summarized-properties)
> * [Pseudo elements](#pseudo-elements)
> * [Don't use @import](#don't-use-@import)
> * [Don't use !import](#don't-use-!import)
> * [Nesting with Preprocessor](#nesting-with-preprocessor)
> * [Sass syntax](#sass-syntax)
> * [@import](#@import)
> * [Quotes](#Quotes)
> * [Float values](#float-values)
> * [Background URL](#background-url)
> * [Attribute values](#attribute-values)
> * [Selector structure](#selector-structure)
> * [Organization](#Organization)

## Introduction
> It was used a join naming concepts used by `SMACSS`, `BEM`, `SUIT CSS` for a more modular approach of the components.
> Based on Sass with `SCSS` as a `CSS` syntax of the preprocessor. Using `Compass` to help develop, as prefixes and generating `CSS sprites`.

## Syntax

* Use soft tabs with two spaces—they're the only way to guarantee code renders the same in any environment.
* When grouping selectors, keep individual selectors to a single line.
* Include one space before the opening brace of declaration blocks for legibility.
* Place closing braces of declaration blocks on a new line.
* Include one space after `:` for each declaration.
* Each declaration should appear on its own line for more accurate error reporting.
* End all declarations with a semi-colon. The last declaration's is optional, but your code is more error prone without it.
* Comma-separated property values should include a space after each comma (e.g., `box-shadow`).
* Don't include spaces after commas within `rgb()`, `rgba()`, `hsl()`, `hsla()`, or `rect()` values. This helps differentiate multiple color values (comma, no space) from multiple property values (comma with space).
* Don't prefix property values or color parameters with a leading zero (e.g., `.5` instead of `0.5` and `-.5px` instead of `-0.5px`).
* Lowercase all hex values, e.g., `#fff`. Lowercase letters are much easier to discern when scanning a document as they tend to have more unique shapes.
* Use shorthand hex values where available, e.g., `#fff` instead of `#ffffff`.
* Quote attribute values in selectors, e.g., `input[type="text"]`. They’re only optional in some cases, and it’s a good practice for consistency.
* Avoid specifying units for zero values, e.g., `margin: 0;` instead of `margin: 0px;`.
* Utilization hyphen to separate words in large or compound names.

```sass
// Not
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

// Yes
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```
* <b>Use underscores to separate a block of an element</b>. A block (or an element) must have a unique "name" (a `CSS` class) that could be used in a `CSS` rule. `CSS` class for an element is a block name and an element name separated by a hifen.

* It is necessary to include block name into a `CSS` class for an element to minimize cascading. It is also important to use tabs consistently to allow developers able indentificar an element unequivocally, no errors. We use hyphen to separate words in long names (for example, block-name) and one underscores to separate the name of the block form the name of the element:
```sass
.block-name_element-name {}
.nav_nav-bar  {}
.menu_item    {}
.block_header {}
.figure_img   {}
.form-contact_fieldset{}
```
* <b>Use double hyphen to structure modifiers</b>. A modifier component is a class that modifies the presentation of the core component in some way (for example, for a given component configuration). Change names must be separated from the component name by two hyphens:
```sass
.button--big    {}
.button--small  {}
.button--large  {}
.box--expanded  {}
.sidebar--right {}
.block--12-colun{}
```
* <b>Use the `is-` prefix to indicate the state of that element</b>. A state is something that augments and overrides all other styles. For example, a message may be in a success or error state.

* The msg module is simple enough and has an error state applied to it. One could imagine a success state could be applied to the message, alternatively. Finally, the field label has a hidden state applied to hide it from sight but still keep it for screen readers. In this case, we are actually applying the state to a base element and not overriding a layout or module.
```sass
.is-active    {}
.is-hidden    {} 
.is-visible   {} 
.is-open      {} 
.is-close     {} 
.is-expanded  {} 
.is-collapsed {} 
.is-disabled  {}
.is-tab-active{}
.is-error     {}
.is-success   {}
```

## Indenting
With individual declarations should proceed in order to indicate a heritage of the class, thereby making the child elements have a retreat twice the element or parent class and so on. But beware, care for it is not too used to the code do not be unproductive having to give many setbacks, use common sense.

<b>CSS<b/>
```sass
.menu {}

  .menu_list {}
    
    .menu_iten {}
```
<b>SASS<b/>

`Sass` provides nesting functionality. That is to say, by writing this:
```sass
.menu {
  .menu_list {
    .menu_iten {
      color: blue;
    }
  }
}
```
…we will be left with this compiled `CSS`:
```sass
.menu .menu_list .menu_iten { color: blue; }
```

## Comments
Code is written and maintained by people. Make sure that the code is descriptive, well commented and friendly to others. Large chunks of reviews must have context and should not only reiterate one class or component name.

<big><b>We adopted the comments used by `SASS`.</b></big>

<b>Example with `SASS`:</b>
```sass
//  ==========================================================================
//  Section comment block
//  ==========================================================================

//  Sub-section comment block
//  ==========================================================================

//  
//  Short description using Doxygen-style comment format
//  
//  The first sentence of the long description starts here and continues on this
//  line for a while finally concluding here at the end of this paragraph.
//  
//  The long description is ideal for more detailed explanations and
//  documentation. It can include example HTML, URLs, or any other information
//  that is deemed necessary or useful.
//  
//  @tag This is a tag named 'tag'
//  
//  TODO: This is a todo statement that describes an atomic task to be completed
//  at a later date. It wraps after 80 characters and following lines are
//  indented by 2 spaces.
//  

//  Basic comment
```

<b>Example with `CSS`:</b>
```sass
/* ==========================================================================
   Section comment block
   ========================================================================== */

/* Sub-section comment block
   ========================================================================== */

/*
 * Bloco de comentário de grupo
 * Ideal para explicações em múltiplas linhas e documentação.
 */

/**
 * Short description using Doxygen-style comment format
 *
 * The first sentence of the long description starts here and continues on this
 * line for a while finally concluding here at the end of this paragraph.
 *
 * The long description is ideal for more detailed explanations and
 *  documentation. It can include example HTML, URLs, or any other information
 *  that is deemed necessary or useful.
 *   
 *  @tag This is a tag named 'tag'
 *   
 *    TODO: This is a todo statement that describes an atomic task to be completed
 *    at a later date. It wraps after 80 characters and following lines are
 *    indented by 2 spaces.
 */

/* Basic comment */
```

## Declarations
In places where they are defined only one line of property, consider removing line breaks to improve reading and editing.

Already in places where there is more than one value for a single property, consider breaking the line to better visualize each value.

```sass
// Only statement on a line
.selector-1 { width: 10%; }
.selector-2 { width: 20%; }
.selector-3 { width: 30%; }

// Declaration multiple lines
.sprite {
  display: inline-block;
  width: 16px;
  height: 15px;
  background-image: url(../img/sprite.png);
}

// Not
.selector {
  background-image: linear-gradient(#fff, #ccc), linear-gradient(#f3c, #4ec);
  box-shadow: 1px 1px 1px #000, 2px 2px 1px 1px #ccc inset;
}

// Yes
.selector {
  background-image:
    linear-gradient(#fff, #ccc),
    linear-gradient(#f3c, #4ec);
  box-shadow:
    1px 1px 1px #000,
    2px 2px 1px 1px #ccc inset;
}

```

## Order of declarations
Statements must be ordered by a single principle. The preference is related properties to be grouped and structurally important properties (for example, positioning and box-model) to be declared before typeface properties, or background color.

```sass
.selector {
  // Positioning 
  position: absolute;
  z-index: 10;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;

  // Display & box model
  display: inline-block;
  overflow: hidden;
  box-sizing: border-box;
  width: 100px;
  height: 100px;
  padding: 10px;
  margin: 10px;
  
  // Typography
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  // Visual
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  // Other
  opacity: 1;
}
```

## Summarized properties
Esforce-se muito para usar declarações de propriedades resumidas onde você define todos os valores dessa propriedade. As propriedades resumidas mais usadas incluem:

* `padding`
* `margin`
* `font`
* `background`
* `border`
* `border-radius`

```sass
// Not
.element {
  margin-bottom: 10px;
  background-color: red;
  background-image: url("image.jpg");
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}

// Yes
.element {
  margin: 0 0 10px;
  background: red url("image.jpg");
  border-radius: 3px 3px 0 0;
}
```

## Pseudo elements
Pseudo elements should be accessed by using a single colon `:`. Do not use double colons `::`.

```sass
// Not
.button::before {
  outline: 0;
}

// Yes
.button:before {
  outline: 0;
}
```

## Don't use @import
Compared to `<link>`s, `@import` is slower, adds extra page requests, and can cause other unforeseen problems. Avoid them and instead opt for an alternate approach:

* Use multiple `<link>` elements
* Compile your `CSS` with a preprocessor like `Sass` or `Less` into a single file
* Concatenate your `CSS` files with features provided in `Rails`, `Jekyll`, and other environments

```html
<!-- Not -->
<style>
  @import url("style.css");
</style>

<!-- Yes -->
<link rel="stylesheet" href="style.css">
```

## Don't use !import
The `!Important` causes a property ignore any specific rule selector. That is, a property within a weight selector 1, can "win" another property in a weight selector 111. You can win up to a defined inline property! <b>So never use if you want your code to be scalable</b>.

* In `print.css` where you need to really force a definitive style. In this case, no further rules will need to override the rules defined in `print.css`, so you have full control of what you are doing.

* In other situations the `!Important` may be necessary, as to override styles out of your control. For example, if you are editing a template on a platform where there is no access to the original `CSS`, but can inject a new `CSS` to override some styles. Or, if this platform uses some inline styles you want to overwrite. But note that this is a case totally out of context scalable `CSS`. You do not have control over the `CSS`, it will not scale that way.

```sass
// Not, Not, Not...
.one-half {
    width: 50% !important;
}

// Not, Not, Not...
.hidden {
    display: none !important;
}
```

## Nesting with Preprocessor
Avoid nesting selectors (to "nesting"). Just because you can do it, does not mean you should do it always. It is a good practice ultilizar `class` `tags` and not even using` class` avoid using more than two nested `class`.

```sass
// Not
.table > thead > tr > td { … }

// Yes
.table        { … }
.table_thead  { … }
.table_line   { … }
.table_column { … }
```

## Sass syntax

Should serseguido the SCSS Sass syntax. Do not write code that follows the SASS syntax.

```sass
// Not
.menu
  &.is-open
    display: block;
    
// Yes
.menu {
  &.is-open {
    display: block;
  }
}
````

## @import
Use double quotes to call it the modules " ".

```sass
// Not
@import base/reset.scss;

// Yes
@import "base/reset.scss";
```

## Quotes
Use double quotes ever.

```sass
// Not
.selector:after {
  content: 'Lorem Ipsum';
}

// Yes
.selector:after {
  content: "Lorem Ipsum";
}
```

## Float values
Don't prefix float values with a leading zero.

```sass
// Not
.sidebar {
  right: -0.85px;
}

// Yes
.sidebar {
  right: -.85px;
}
```

## Background URL
Quote background urls.

```sass
// Not
.selector {
  background: url(url/imagem.png) no-repeat;
}

// Yes
.selector {
  background: url("url/imagem.png") no-repeat;
}
```

## Attribute values
Quote attribute values in selectors.

```sass
// Not
input[type=radio] {
  display: none;
}

// Yes
input[type="radio"] {
  display: none;
}
```

#Selector structure
Add a line break after `@extend`/`@include`, `variables`, `functions`/`placeholders`/`mixins` and other rules.

```sass
// Not
.selector {
  @extend centered-content;
  @include font-smoothing;
  $color: red;
  %inner-placeholder {
    // ...
  }
  @mixin inner-mixin {
    // ...
  }
  border: 1px solid gray;
}

// Yes
.selector {
  @extend centered-content;
  @include font-smoothing;

  $color: red;

  %inner-placeholder {
    // ...
  }

  @mixin inner-mixin {
    // ...
  }

  border: 1px solid gray;
}
```

#Organization
* The order of declaration should look like:
	1. `@extend` 
	2. `@import`
	3. Variable definitions
	4. Functions, placeholders and mixins
	5. Other rules

```sass
// Bad
.button {
  border: 3px solid seagreen;
  @include border-radius(5px);
  background: fuchsia;
  @extend %button-base;
}

// Yes
.button {
  @extend %button-base;
  @include border-radius(5px);

  border: 3px solid seagreen;
  background: fuchsia;
}

// Not
.square {
  @include border-radius(3px);
  @extend %shape-base;
  @include box-sizing(border-box);
  @extend %square-base;
  // Other rules
}

// Yes
.square {
  @extend %shape-base;
  @extend %square-base;
  @include border-radius(3px);
  @include box-sizing(border-box);

  // Other rules
}

// Not
.selector {
  border: 0;
  @include font-smoothing;
  @mixin inner-mixin {
    // ...
  }
  @extend centered-content;
  %inner-placeholder {
    // ...
  }
  $color: red;
}

// Yes
.selector {
  @extend centered-content;
  @include font-smoothing;

  $color: red;

  %inner-placeholder {
    // ...
  }

  @mixin inner-mixin {
    // ...
  }

  border: 1px solid gray;
}
```
