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

Spacing
-------


I like some room between sections, 5 clear lines is usually enough.

Between sub-sections and other chunks of code within a section, I'll use 3 clear lines.

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

