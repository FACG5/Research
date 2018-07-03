# CssResearch

# Mobile First Design 
- What is Mobile first Design ? 
Mobile-First design strategy allows the mobile site development (the most involved version) to be created first, followed by the tablet and desktop versions.

- Why “Mobile First” Principle Is So Important in Product Design?
= we have more tangible reasons to believe that mobile-first principle is important in  
 product design. That is, the exploding of mobile use .
= Mobile internet usage has surpassed desktop usage in 2016.
= People have spent more and more time on the internet from mobile ends.

- what are the Benifits ? 
= Define a clear site navigation.
= Focus on the content into a simple and concise format 


- Explain

 - Mobile First Design is an approach to responsive design, where you make a design for mobile screens, or smaller screens first and then add added features and content for larger screens.

- The two aren’t mutually exclusive.

***






# What is CSS?
- CSS stands for Cascading Style Sheets
- CSS describes how HTML elements are to be displayed on screen, paper, or in other media
- It can be inline, internal and external
- CSS saves a lot of work. It can control the layout of multiple web pages all at once
**External stylesheets are stored in CSS files

# CSS With BEM
BEM (stands for Block-Element-Modifier) 
Is a naming convention standard for CSS class names.
useful in writing CSS that is easier to read, understand, and scale.
---
# Why BEM
benefits:
-communicates purpose or function
-communicates component structure
-sets a consistent low-level of specificity for styling selectors

# How It Works
includes up to three parts:

-Block: The outermost parent element of the component is defined as the block.
-Element: Inside of the component may be one or more children called elements.
-Modifier: Either a block or element may have a variation signified by a modifier.
If all three are used in a name it would look something like this

                    [block]__[element]--[modifier]--


```css
/* Block component */
.btn {}

/* Element that depends upon the block */ 
.btn__price {}

/* Modifier that changes the style of the block */
.btn--orange {} 
.btn--big {}

```
In this CSS methodology a **block** is a top-level abstraction of a new component, for example a button: `.btn { }`. This block should be thought of as a parent. Child items, or **elements**, can be placed inside and these are denoted by two underscores following the name of the block like `.btn__price { }`. Finally, **modifiers** can manipulate the block so that we can theme or style that particular component without inflicting changes on a completely unrelated module. This is done by appending two hyphens to the name of the block just like `btn--orange`.
