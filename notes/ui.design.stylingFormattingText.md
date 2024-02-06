---
id: k4htnyvdkcb3d9v1p9fivdy
title: Styling Formatting Text
desc: ''
updated: 1701230171188
created: 1688650129441
---

## Vertical Grid

The **first thing we are going to do when designing an app is choosing the body typography** because this will influence the line height of the body text and the line height will influence the vertical rhythm for the whole application

Baseline grid is a layout grid where the baseline of each line of text aligns with the grid but this is impossible in web design because as we seen before the text has a line height that usually never aligns with the baseline, which means alignment based on this baseline is untranslatable to css

Therefore we will use another concept called **vertical grid in which we account for this line height and we base our vertical rhythm on it**, `the line height usually dictates the size of our grid`

![](/assets/images/UI/vertical-grid-line-height.png){max-width: 600px}

> the grid size doesn't have to be the exact number of our line height, it can also be any number that divides it if our line height is 18 the grid can be 18, 9, 6, 3, 2

Take this example we choose *Convergence* typeface at 13px as our body text, our line height which is the blue box visible when you select text will give us a roughly 18px **vertical grid size that we can round for easier use**, **once we choose our vertical grid we make sure all our other elements align to this grid**, our title font *Concert One* is set to 32px because its line height aligns exactly with our grid, and our button is also set to fill exactly 3 rows of the grid

![](/assets/images/UI/vertical-grid-padding.png){max-width: 600px}

**We can also calculate our paddings between elements using this grid**, we know between the text paragraphs there is a 18px padding, and between the text to button or title there is a 36px padding which we can easily replicate in css, and even calculate the top and bottom paddings if needed

When we remove all our guidelines we are left with a vertically aligned flow

![](/assets/images/UI/vertical-grid-post.png){max-width: 600px}

> Make sure to design for your prefered device first because we will probably have to make some sacrifices for the other devices in order to meet deadlines

## Visual Hierarchy

We need to **build a visual hierarchy in our typographic system**, some of the tools we can use to increase elements visual hierarchy are:

* Make things **bigger**
* Make things **bolder**
* **Center** the most important thing, everything else should be left aligned
* Add **more white area** so elements occupy more space
* Use **all cap**s text
* Use **different colors** to create hierarchy groups
* Use **different fonts** to create hierarchy groups
* Use **background color** to change the contrast
* Increase the **letter spacing**

## Type Scale

Once we decided our body text dimensions we can use different scale tools like [Type Scale](https://typescale.com/) to help us pick the size of or heading and caption text, using **scales can help the uniformity and consistency of our composition**

**Most of the scales available to choose from are musical scales because they feel natural** to us, but we can also use the golden ratio scale that uses fibbonaci with [Golden ratio calculator](https://grtcalculator.com/)

![](/assets/images/UI/convergence-golden-ratio.png){max-width: 600px}

After using this calculators you will get some rough number to guide you, but as everything else **dont be afraid to tweak things up a bit, this is just a guideline**

## Create a Type Scale

Now that we have our font sizes, line heights and vertical grid we can figure out our text margins, which means we will **assign our different text size with a matching white space**

For the type scale you should fill all the different types of text available in html components, which means **make sure you have standards for text h1 to h6, p, and span in your type scale**

![](/assets/images/UI/convergence-type-scale.png){max-width: 600px}

To **make sure this margins work well using a mockup** with no additional padding other than the ones you assigned to each font size, and make the necessary tweaks and dont be afraid to even ignore the grid if necessary

Now complete your type scale **enforce the visual hierarchy of the scale changing other properties of the text, choose different colors or shades of the same color, choose different boldness** and assigned them to the different elements in your type scale

![](/assets/images/UI/convergence-example-composition-color-hierarchy.png){max-width: 600px}

## Design System

A design system is a **set of rules, guidelines and principles set in place to enforce a cohesive look and feel of our applications**, and the correct use of our components and patterns

A good place to start looking for inspiration on others design system is [Design Systems Repo](https://designsystemsrepo.com/) where you can find different companies type systems, one of the most interesting ones is Google Material Design

## Open type features

Some fonts have open type features which means it will **let us vary some properties that most other fonts dont even consider**, we can find this features on figma by clicking the 3 dots button on the text bottom right side menu

![](/assets/images/UI/figma-open-type-features.png){max-width: 300px}

### Ligatures

Are glyphs created when two or more letters are joined together, including mathematic symbols

![](/assets/images/UI/open-type-ligatures.png){max-width: 300px}

This **ligatures are not a standard, are extra glyphs that only some fonts include** and can be activated or deactivated but the provided font file needs to be .otf or .woff format, older formats may not dont support this extra symbols

### Small Caps

Are glyphs sized to the x-height but with Caps appareance

![](/assets/images/UI/open-type-ligatures.png){max-width: 300px}

This **small caps are not a standard, are extra glyphs that only some fonts include** and can be activated or deactivated but the provided font file needs to be .otf or .woff format, older formats may not dont support this extra symbols

### Letter Spacing

Is the ammount of space between each letter, it's usually used in oversized letters to fix big titles 

Another common use is on bulky letters to reduce density or help the visual hierarchy

![](/assets/images/UI/open-type-letter-spacing.png){max-width: 300px}

### Kerning 

The difference between the space of different letters **is the whole area between two letters** and its aimed to be the same for any to letters

Letting the browser or other softwares to automatically calculate the kerning for each letter combination can be quite tricky and leave some weird spacing, so **some high quality fonts have kerning tables embeded on the font file** to identify what the gap should be between each letter combination

You can practice spotting kerning mistakes on [Kerning Game](https://type.method.ac/)

### Paragraph Alignment

Paragraphs on the web have different qualities and rules than paragraphs on pages because our reading habits on the we are quire different, including

* Paragraphs should be shorter on the web
* Paragraphs should be as self contained as possible, which means one should be able to skip paragraphs without issue and they still make sense
* Text is usuallt justified left
* Centralized text seems more authorative but is only used in short paragraphs because on larger text it makes the reading experience slower
* We dont need to worry about orphaned words

### Numbers and Dates

Not all fonts have number glyphs so make sure the font you are using includes every glyph you will need.

M**ost number glyphs by default are Lining numbers which are like upper case** numbers and therefore are bigger than the x-height, but we can switch this in some forms to use **Old-Style numbers which are like lower case** numbers if we want a more seamless transition between numbers and text

![](/assets/images/UI/open-type-numbers-and-dates.png){max-width: 300px}

On another note remember numbers should normally be right aligned and you might want to use the monospaced version if you want users to be able to compare numbers faster

## Styling

You can find fonts that have different heights and **although it is good to use this variants for our different text necessities dont go overboard**

* If a text is too big dont use the boldest weight
* If a text is too small dont use the thinest weight
* If you use a really dense text try using a lighter color to correct this

This can affect legibility and create a unclosable gaps on our hierarchy making our type scale look disorganized

## Typography System

When creating a typography system is important to **think about all the posible text uses you might encounter in your application and use real content mockups** to get a feeling of how your system works in real conditions




