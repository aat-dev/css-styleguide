CSS Style Guide
===============

## General   

 - Use UTF-8 encoding.
 - Indents are two spaces.
 - Lines with nothing on them should have no whitespace.
 - There should be no whitespace at the end of a line.

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
    

