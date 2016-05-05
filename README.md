CSS Style Guide
===============
Welcome to the AAT Lab CSS style guide. Before reading this you should have a general understanding of CSS and the SCSS.

## General   

- Use UTF-8 encoding.
- Indents are two spaces.
- Lines with nothing on them should have no whitespace.
- There should be no whitespace at the end of a line.
- Be consistant about where spaces before/after colons/braces go
- One selector per line, One rule per line
- List related properties together
- Have a plan for class name naming(Explained the BEM methodology bellow)

- list @extents first
- list @includes next
- list regular styles next
- Nested Pseudo Classes and Pseudo Elements Next
- Nested selectors Last

- Variablize All Colors
- Variablize sites Font Families
- Variablize All Font sizes

- Never Write Vendor Prefixes
- Maximum Nesting: Three Levels Deep
- Maximum Nesting: 50 Lines

- Global and Section-Specific Sass Files Are just Table of Contents
- List Vendor/Global Dependencies First, Then Author Dependencies, Then Patterns, Then Parts
- Break Into As Many Small Files As Makes Sense
- Partials are named _partial.scss

- Locally, Compile with Source Maps
- In Deployment, Compile Compressed
- Don't Commit .css Files
- Be Generous With Comments

## Tools
 
We using the following tools and best practice :  
 
 
## SASS Preprocessor 

We use Sass (Syntactically Awesome Stylesheets); which is a scripting language that is interpreted into Cascading Style Sheets (CSS).

- [http://sass-lang.com/](http://sass-lang.com/) 
- [http://sass-lang.com/libsass](http://sass-lang.com/libsass)


## Framework

 - Bootstrap (Current 3.x - http://getbootstrap.com/)

## SMACSS

We're aiming to stick to Jonathan Snook's SMACSS principles for structuring our CSS.

Here is a summary of the SMACSS principles, divided by its rule types : 

#### base rules

- default, single-element selectors
- could just be a reset stylesheet

#### layout rules

- divide the page into sections, holding modules together

#### module rules

- reusable, modular parts of designs
- should each exist as a standalone component
- avoid conditional styling based on location
- if you need this, sub-class the module

*Please see for a more detailed reference :* 

- [https://smacss.com/](https://smacss.com/) 

## BEM

This is well-documented on the official site, but here is a brief introduction to **BEM (stands for Block, Element, Modifier).**

- [http://getbem.com/introduction/](http://getbem.com/introduction/)

As for naming conventions, we use a BEM-like notation.

- Block (e.g.: navigation)
- Element (e.g.: item)
- Modifier (e.g.: active)

*With this naming convention:*

    component-name {}
    component-name--modifier-name {}
    component-name__sub-object {}
    component-name__sub-object--modifier-name {}

*We would have:*

    .navigation {}
    .navigation__item {}
    .navigation__item--active {}

More information about BEM and its benefits : 

- [https://robots.thoughtbot.com/keeping-the-frontend-modular-with-bem](https://robots.thoughtbot.com/keeping-the-frontend-modular-with-bem)
- [http://blog.kaelig.fr/post/48196348743/fifty-shades-of-bem](http://blog.kaelig.fr/post/48196348743/fifty-shades-of-bem)
- [https://css-tricks.com/snippets/sass/bem-mixins/](https://css-tricks.com/snippets/sass/bem-mixins/)
    
### BEM Mixins

We have two wrapper mixins for our BEM syntax as following:

```
/// @param {String} $element - Element's name
@mixin element($element) {
    &__#{$element} {
        @content;
    }
}
```

```
/// @param {String} $modifier - Modifier's name
@mixin modifier($modifier) {
    &--#{$modifier} {
        @content;
    }
}
```
#### Example:
Rewriting our previous BEM example with our brand new mixins:

```
.navigation{ 
    /* CSS declarations for `.navigation` */
    @include element('item') {
        /* CSS declarations for `.navigation__item` */
    }
 }
 ```
 
 ```
 .navigation{ 
    /* CSS declarations for `.navigation` */
    @include element('item') {
      /* CSS declarations for `.navigation__item` */
       @include modifier('active') {
         /* CSS declarations for `.navigation__item--active` */
    }
 }
 ```



### BEM Mixins & Bootstrap Framework

Please use following approach when using Bootstrap style with the custom BEM work.  (@extend is preferred when not creating new elements)

@import : 

    .navigation {
    
      @include make-row();
    
      .navigation__icons {
        @include make-sm-column(6);
      }
    
      .navigation__links {
        @include make-sm-column(6);
    
        }
    }


@extend : 

    .navigation {
    
      @extend .row;
    
      .navigation__icons {
          @extend .col-md-6;
      }
    
      .navigation__links {
         @extend .col-md-6;
       }
    }
    
*/ Available variables for Font Families:
 ```
$base-font-family: Arial, Helvetica, sans-serif;
$heading-font-family: 'Trade Gothic W01', Arial, Helvetica, sans-serif;
 ```
*/ Available variables for Font Sizes:
 ```
$font-size-base: 14px !default;
$font-size-large: ceil(($font-size-base * 1.25)) !default; // ~18px
$font-size-medium: ceil(($font-size-base * 1.15)) !default; // ~16px
$font-size-small: ceil(($font-size-base * 0.85)) !default; // ~12px

// Heading font sizes
$font-size-h1: floor(($font-size-base * 2.15)) !default; // ~30px
$font-size-h2: floor(($font-size-base * 1.8)) !default; // ~25px
$font-size-h3: ceil(($font-size-base * 1.6)) !default; // ~22px
$font-size-h4: floor(($font-size-base * 1.15)) !default; // ~16px
$font-size-h5: $font-size-base !default; // 14px
$font-size-h6: ceil(($font-size-base * 0.85)) !default; // ~12px
 ```
Variables for Colours:
 ```
// Legacy
$darkgrey: #333;
$lightgrey: #dcdcdc;

// Primary colours
$aat-green: #00AB4E;
$aat-grey: rgb(124,124,123);

//AAT text color
$aat-text: #64696E; //Shade of Gray

// Secondary colours - 2014 NEW
$aat-blue: #0097DE;
$aat-teal: #007C81;
$aat-turq: #00BB9D;
$aat-yellow: #FFC723;
$aat-mauve: #880060;

// Tints of Secondary colours - 2016
$aat-blue-light: lighten($aat-blue, 20%); //#45c4ff
$aat-blue-dark: darken($aat-blue, 20%); //#0074ab
$aat-teal-light: lighten($aat-teal, 10%); //#00adb4
$aat-teal-dark: darken($aat-teal, 10%); //#004b4e
$aat-turq-light: lighten($aat-turq, 20%); //#22ffdc
$aat-turq-dark: darken($aat-turq, 15%); //#006f5d
$aat-yellow-light: lighten($aat-yellow, 10%); //#ffd456
$aat-yellow-dark: darken($aat-yellow, 10%); //#efb200
$aat-mauve-light: lighten($aat-mauve, 10%); //#bb0084
$aat-mauve-dark: darken($aat-mauve, 10%); //#55003c

// Secondary colours - PRINT OLD
$aat-duckegg: #82cec1;
$aat-aqua: #00b7de;
$aat-violet: #672f87;
$aat-mustard: #ffc222;
$aat-berry: #d15980;

// Aqua shades
$aat-aqua-50: #97E1F1; //Aqua

// Utility colours
$aat-default: #2a2a2a; // Black
$aat-option: #999; // Grey
$aat-success: #00ab4e; // Green
$aat-warning: #F28300; // Amber
$aat-danger: #EB5050; // Red
$aat-danger-1: #ff0044; // Red
$aat-cta: #F28300; // Orange
$aat-cta-border: #d07100; // Orange - border/box shadow
$aat-cta-hover: #ff8c04; // Orange - hover/active

//New frontpage custom colours
$aat-cta: #F28300; // Orange
$aat-cta-border: #d07100; // Orange - border/box shadow
$aat-cta-hover: #ff8c04; // Orange - hover/active

//Transtional widget AQR24 - custom colours
$aat-tw: $aat-turq;
$aat-tw-border: $aat-teal; // border/box shadow
$aat-tw-hover: $aat-teal; // hover/active

// Greyscale
$gray-darker: darken($aat-grey, 30%);
$gray-dark: darken($aat-grey, 20%);
$gray: $aat-grey;
$gray-light: lighten($aat-grey, 20%);
$gray-lighter: lighten($aat-grey, 30%);
$gray-lightest: lighten($aat-grey, 45%);

// Custom greys
$gray-xxlighter: #f7f7f9;
$aat-grey-lh-nav: #d3d3d3;
$aat-dark-grey-prim-nav: #393939;
$aat-dark-grey-prim-nav-1: #2b2b2b;
$aat-accordion-bg: #f5f5f5;

// Tints
$aat-green-90: #18B25E;
$aat-green-80: #32BA70;
$aat-green-70: #4BC381;
$aat-green-60: #65CB93;
$aat-green-50: #7FD4A6;
$aat-green-40: #98DCB7;
$aat-green-30: #B2E5C9;
$aat-green-20: #CBEDDA;
$aat-green-10: #E5F6EC;

// Link colours
$link-color: $aat-green;
$link-hover-color: darken($link-color, 15%);
 ```

*Available @mixins for Bootstrap 3.x :* 

- container-fixed()
- make-row()
- make-xs-column()
- make-xs-column-offset()
- make-xs-column-push()
- make-xs-column-pull()
- make-sm-column-offset()
- make-sm-column-push()
- make-sm-column-pull()
- make-md-column-offset()
- make-md-column-push()
- make-md-column-pull()
- make-lg-column-offset()
- make-lg-column-push()
- make-lg-column-pull()
- clearfix()
