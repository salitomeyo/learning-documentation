---
id: wupjgb23ere2gy6f7w96lra
title: Grid Systems
desc: ''
updated: 1704494135452
created: 1688650142291
---

## Geometry

In the 1900s geometric typefaces started to take notice and became popular because they where consider easier to read, but in reality we have come to the conclusion they are actually some of the harder typefaces to read because the letters are too similar. This is something we have to take into account when creating our compositions, **even thought geometric shapes and grids may feel pleasing they may not be the best for the user**

The best art pieces have an element of chaos, after creating **our typographic system we can see a natural grid** made out of the typefaces and choices we made, we can **base our grid in this natural grid feeling and make most things align to it**, but if we want our design to pop and be remembered **we also need to be able to break this grid for our compositions**

## Types of grid

### Manuscript Grid

**Were the first grids ever made for books, all the letters of the page fit inside this box**

There are all sorts of variations, the manuscrid grids could be off center, have different margins in every direction

### Column grid

Used **when we have more than one box of text**, this allows a new measurement, the gutter is the space in between two boxes of text

This could include different columns, footers and headers, and any other kind of box of text

Different text box sizes are usually used to represent different types of content

Also take into account that **making our grid doesn't necessarily mean everything on it should be one column wide**, our elements could span accross different columns

### Modular Grid

Is **more like a table, it has rows and columns**, this is usually considered better for web applications

Using a modular grid allows different sections of a web page to **mantain uniformity**

We also can embed grids inside other grids 

## Importance of Grids

Something **off grid feels imbalanced, it prompts anxiety and it feels less professional**, so always try to align elements to a grid

Remember the vertical grid comes from the typography choosen 

Originally web design used a 12 column grid standard, this has been slightly discontinued and designers are prompted to create their own grids and use as many different grids for each sections as needed

## Box Model

Css box model is what each elements consists of on a basis, each css element has border, padding, and margin

* The **Border is an outline**, usually colored to signify the size of the element

* The **Padding is the space between the content and the border**, is used to avoid creating elements that feel busy or are too small (it is included in the element size)

* The **Margin is the space between the border and any other element**, is the separation between elements (it is not included in the element size)

The sizes of the border, padding and margin of each element can be separated into up, down, right and left values and this values can be either the same or completely different from one another or they can be 0

## Flex-Box

Using a flexbox is a css property that allows us to use patters to align, justify and space the elements inside the flexbox vertically and horizontally 

## Css Grid

**CSS grid gives us a lot less control than Flexbox**, but it  allows us to put elements in "tables" of rows and columns with uniform width and height

Each section of our design can use a completely separate grid

## Responsive vs Fluid

In adaptive design you will use different css files for every screen size, but it was not only hard to manage but also became quite harder as other devices started appearing on the market

### Fluid Design

Uses VW units to make typeface sizes adjust to the viewport width

This made things easier for designers but it also lose a lot of freedom, fluid designs accomodate on their own based on the screen size

### Responsive design

It allows the designer to create 3 separate designs that will be used in 3 different instances, each design will have slight alterations to achieve the best possible experience on that size

**This wont accommodate every screen size perfectly but it will fit most of the sizes, this is considered a recommended practice by many but it is important to remember that the 3 screen sizes you design for are the most common sizes** as long as this makes sense for your application

This could be paralelled with fluid title texts 

## Anatomy of the Grid

The grid includes lots of elements but lets list the easily:

* **Vertical Grid**: We already have this from our typeface choices
* **Columns**: They separate our page horizontally (we usually want this columns to be multiple of our vertical grid)
* **Gutter**: The space between each column
* **Margin**: Unvariable space at the sides of our grid
* **Outer Margins**: Are flexible will grow when we hit the maximum width
* **Modular Grid or Units**: Boxes created from intersecting our rows and columns
* **Field**: A group of rows used to break visual monotony, we can call this group of rows or vertical region to avoid confusion
* **Spatial Zone**: Is a group of columns and possibly rows, although it is usually used on other media and not in web development
* **Hang line**: Separes the heading space to the rest of the design
* **Flow Line**: Are visible lines (usually black) aligned to our vertical grid, they are used to draw peoples attention but they add a lot of visual complexity

Is **recommended to put each part of the Grid in a separate layer** in whichever software you are using to avoid confusion because the grid all visible can get quite confusing

Another common suggestion is to never align the text to the borders of an elements, always add some kind of paddind






