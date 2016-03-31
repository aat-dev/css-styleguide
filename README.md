CSS Style Guide
===============

## General   

 - Use UTF-8 encoding.
 - Indents are two spaces.
 - Lines with nothing on them should have no whitespace.
 - There should be no whitespace at the end of a line.

## Tools
 
We using the following tools and practises :  
 
 
### CSS Preprocessor 

 - SASS (Libass - http://sass-lang.com/libsass)

### Framework

 - Bootstrap (Current 3.x - http://getbootstrap.com/)

### SMACSS

 - Please see https://smacss.com/

### BEM

We encourage the use of @snookca's SMACSS framework. This is well-documented on the official site, but here is a brief introduction.

**BEM stands for Block, Element, Modifier.**

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
    

