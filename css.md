## Styleguide Front-End

## Structure CSS
This structure was based on [Idiomatic CSS](https://github.com/necolas/idiomatic-css), [@mdo](http://mdo.github.io/code-guide/), [BEM](http://bem.info/), [SMACSS](http://smacss.com/), [SUIT CSS](https://suitcss.github.io/).

> * [Introduction](#introduction)
> * [Syntaxe](#syntaxe)
> * [Comments](#comments)
> * [Declarations](#declarations)
> * [Order of declarations](#order-of-declarations)
> * [Summarized properties](#summarized-properties)
> * [Nesting with Preprocessor](#nesting-with-preprocessor)
> * [Pseudo elements](#pseudo-elements)
> * [Sass syntax](#sass-syntax)

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

## Comments
Code is written and maintained by people. Make sure that the code is descriptive, well commented and friendly to others. Large chunks of reviews must have context and should not only reiterate one class or component name.

<big><b>We adopted the comments used by `SASS`.</b></big>

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

## ordem de declaracoes
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
  border: 10px solid #333;
  margin: 10px;

  // Other
  background: #000;
  color: #fff;
  font-family: sans-serif;
  font-size: 16px;
  text-align: right;
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

## Nesting with Preprocessor
Avoid nesting selectors (to "nesting"). Just because you can do it, does not mean you should do it always. It is a good practice ultilizar `class` `tags` and not even using` class` avoid using more than two nested `class`.

```sass
// Not
.table > thead > tr > td { … }

// Yes
.table             { … }
.table_thead       { … }
.table_line        { … }
.table_line_column { … }
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

