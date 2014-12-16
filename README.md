Tidy Sass
=========

I do like a tidy stylesheet. When I first found [@csswizardry's](https://twitter.com/csswizardry) 
[CSS-Guidelines](https://github.com/csswizardry/CSS-Guidelines) I loved them and tried to stick to those principles
wherever I could.

Over time though I've refined this to suit my style and this, is the result of that refinement.

***

Purpose
=======

I'm documenting how I write CSS/Sass to help standardise my work across different things I'm working on.

This will help make code easier to understand and maintain in the future.

***

Basics
======

One of the great things about Sass is that you can have a load of _partial.scss files and keep everything nice and clean. Then I use Gulp to minify the css in production.

File Structure
--------------
In my Sass folder there lives just a couple of files:
* master.scss (no styles live here, just import partials)
* _variables.scss (really important file containing all the Sass variables we'll be using in this project)
* _config.scss (allows you to optionally include objects)

Then, I have six folders:
* Tools  (reset, mixins etc.)
* Base (html, body, h1-h6, p, form etc.)
* Layout (grids & wrappers)
* Objects (buttons, icons, media object etc.)
* Modules (header, footer, navigation etc.)
* Pages (page-specific styles—if any)


Naming 'Conventions'
--------------------

I like BEM. I understand how it works in the context of my files and I think it looks quite nice too. I can't say I adhere to it strictly, I just use it where it feels appropriate.

For example:

```
.header {}

.header__contact {}

.header--mobile {}
```

So, header is the BLOCK. header__contact is an element within the header block. header--mobile is an amended version of the header, for mobile.

Read some more on this at http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/



Spacing
-------

I like some room between sections, 5 clear lines is usually enough.

Between sub-sections and other chunks of code within a section, I'll use 3 clear lines.



Order of styles
----------------

I'll always @include and @extend at the start (top). Generally though I don't have an order for styles, recently however I've found myself doing something like this

```
.class {

  // extending and including at the top
  @include border-box();
  @extend %clearfix;

  // position
  display: block;
  position: absolute;
  top: 0px;
  left: 10px;
  z-index: 99;
  float: none;
  clear: right;
  
  // size
  width: 200px;
  height: 50px;
  
  // spacing
  margin: 20px;
  padding: 10px;
  
  // styling
  border: 1px solid white;
  background: red;
  color: white;
  
  // text
  font-size: 16px;
  font-weight: bold;
  text-transform: lowercase;
  
  // everything else
}
```


***

Comments
========


Intro
-----

At the top of each Sass file in the project I put in the title and a brief description. 

```
//  Title of the File
//  =================

//  For:
//  Description of what the file contains
```

Contents
--------

Next comes the contents.

```

//  Section-1...............brief description
//       Sub-Section.........brief description

//  Section-2...............brief description

```

Sections
--------

I start each new section with a large block like this.


```
//------------------------------------//
//  Section-Title
//------------------------------------//
```

Following the title block, I'll then give some more information about the code that follows.
The examples below are optional, I'll just use them as/when needed.

```
//  Hat Tip:
//  Attribution/link to the author etc.

//  Usage:
//  Explain how the code is used (more useful for Mixins)

//  Notes:
//  Anything else
```

Sub-Sections
------------

A sub-section has it's own type of title block. 

```
// 
//  Sub-Section
//
```


Inline Comments
---------------
I only ever use single line commenting - I just think it looks neater.

``
//  comment goes here
``
***

Media Queries
=============

Breakpoints are set in _variables.scss. These are generally $mobile, $tablet and $desktop for larger breakpoints.

In some of my older projects there'll be a media folder containing a new partial for each breakpoint, which are @import -ed in the master.scss file.

BUT things changed and I'm reverting back to inline media queries. I just think they make things a bit clearer and using a version of [@StuRobson's](https://twitter.com/sturobson) excellent [media query mixin](http://alwaystwisted.com/post.php?s=2013-04-01-my-media-query-mixin) makes it a bit of a doddle. We'll see how it goes.
