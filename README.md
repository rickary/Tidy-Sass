Tidy CSS/Sass
=============

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

File Structure
--------------

In my main Sass file you'll find _variables and a couple of 'main' files (typically screen.scss, ie.scss etc.)

I then have three folders:

1. Media (for _bp1, _bp2 etc.)
2. Tools (for mixins, helpers and basic styled objects/modules)
3. Theme (styles specific to this site - see below)

The Theme will usually contain 4 files

* Form (for extending base form styles)
* Typography (all the base type, links, quotes etc. plus importing fonts & icons)
* Site (site-wide elements e.g. body, .container, .header, .footer etc.)
* Pages (everything else that makes up the site, starting with common elements through to page specific stuff)

NOTE: Considering splitting the _page file into _objects and _theme (objects will contain the classes for reusable objects, everyhting else would go in theme)



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

At the top of each sass file in the project I put in the title and a brief description. 

```
// Title of the File
// =================

// For:
// Description of what the file contains
```

Contents
--------

Next comes the contents.

```
//
//	 Section-1...............brief description
//       Sub-Section.........brief description
//   Section-2...............brief description
//
```

Sections
--------

I start each new section with a large block like this.


```
//------------------------------------//
//    !Section-Title
//------------------------------------//
```

*The __!__ works to allow you to quickly search for a section. 
__!__ is particularly useful if you use Coda 2 as this places a manual bookmark in your code that shows up in the insepctor.*

Following the title block, I'll then give some more information about the code that follows.
The examples below are optional, I'll just use them as/when needed.

```
// Hat Tip:
// Attribution/link to the author etc.

// Usage:
// Explain how the code is used (more useful for Mixins)

// Notes:
// Anything else
```

Sub-Sections
------------

A sub-section has it's own type of title block. 

```
// 
// ! -Sub-Section
//
```

The space after the __!__ also shows up in Coda 2 and creates a nicely indented bookmark in the file inspector.

Inline Comments
---------------
I only ever use single line commenting - I just think it looks neater.

``
//	comment goes here
``
***

