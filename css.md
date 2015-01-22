## Styleguide Front-End

## Structure CSS
This structure was based on [Idiomatic CSS](https://github.com/necolas/idiomatic-css), [@mdo](http://mdo.github.io/code-guide/), [BEM](http://bem.info/), [SMACSS](http://smacss.com/), [SUIT CSS](https://suitcss.github.io/).

> * [Introduction](#introduction)
> * [Syntaxe](#syntaxe)
> * [Comments](#comments)

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
