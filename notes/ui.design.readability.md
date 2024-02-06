---
id: 7yhwtip0dkt8dcx6s27vji4
title: Readability
desc: ''
updated: 1700929887021
created: 1688650106688
---

## How we read

The are two different kinds of reading:

* When you are trying to find something, you know what you are looking for and use the text to help you identify it
* When you are trying to extract information, you are trying to understand the information presented

Toni Boson a speed reading champion says there are seven stages to reading

1. **Recognition**: Which is basically identifying the letters on the page
2. **Assimilation**: Physical part of reading which is light been transported from your eye to your brain
3. **Comprehension**: Understand what the words say, what is the meaning of the words
4. **Knowledge**: When we integrate what we read with what we already know, maybe we form an opinion
5. **Retention**: Being able to store the information read
6. **Recall**: Being able to access the stored information when needed
7. **Communication**: Being able to use that information and explain it to somebody else

We need to **consider this stages before choosing a typeface**, for example take the first two stages against helvetica; Helvetica looks simple, uses basic grometric shapes and is easy to assimilate but some of the letters are far too similar like the lower case l and the upper case I, the h ascender is almost the same high as the n

Just using this stages can make us realize **Helvetica is a great choice for assimilation but a terrible choice for recognition**

And even though i**t may seem overkill to find every single glyph in a typeface and criticize or prize it base on this stages take into account that almost no adult looks at every single letter**, reading if you are fast enough basically transforms into glancing at the overall shape of a word to identify it

Then **choosing a typeface while taking into consideration this tiny details seems massively important specially for large bodies of text**

## Readability

**The way people measure readability is almost as wide as the way people gauge usability**, but there are tools like [Readable](https://readable.com/) you can use to find a more comprehensive overview

As web typographers we need to think about the variables available, the variables we can control

* Text Size
* Line Lenght
* Line Height

There is no rule of thumb to figure out how to make this variables work for us, but changing one of them will affect the others so **readability for us is how well the text size, line lenght and line height complement each other**

## Aspect Ratio

If you take any typeface you can find the aspect ratio:

$$
aspectRatio = \frac{height}{xHeight}
$$

it usually is around 0.5, when choosing a typeface you can figure out the aspect ratio doing calculations or use tools like [Aspect ratio calculator](https://clagnut.com/sandbox/font-size-adjust-ex.html) when you have the font installed on your computer

![](/assets/images/UI/convergence-aspect-ratio.png){max-width: 600px}

## Viewing Distance

We dont want to keep measuring things in pixels because we are now working with reference pixels, which mean different devices have different reference pixel size

> Designers shouldn't care about the real world, it doesnt matter the ammount of pixels, but rather people perception on those pixels

Our new pixels called perceptual pixels are a concept already used in areas like astronomy called arc minutes

### Arc Minute

`Is the number of degrees that earth turns in one minute, which is aproximately 1/60 of a degree`, this is basically what we can perceive and we will use arc minute as our perceptual pixel unit

We can indicate arch units using any of the following:

* 48´
* 48am
* 48amin
* 48arcmin

**If something is less than half the size of an arc minute we cant see it**, we use arc minutes because the distance from our eye makes a big difference on how well we can see it

Which means pixels not only vary on the display but on the distance that display is from our eyes some common distances are:

* **Monitors** are typically 60cm from our face, which means 16 pixel would be 24 arc minutes
* **Tablets** are tipically 45cm from our face, which means 16 pixel would be 36 arc minutes
* **Phones** are tipically 30cm from our face, which means 16 pixel would be 48 arc minutes

So basically `arc pixels account for the fact that closer things usually have a higher resolution` and therefore things further away should be bigger

We can use this arc pixels to figure out if something is readable or perceivable, and we can perform the needed calculations using tools like [Size calculator](https://sizecalc.com/) to figure out the physical size required based on an agreed on arc minutes and view distance

Is usually agreed upon that **20-22 arc minutes are a comfortable reading size** so we can use this value when performing calculations

We can also use reference pixels as our perceived size unit applying the following convertions if needed

$$
1 Reference Pixel = 1.2789 arc min 
$$

$$
1 Reference Pixel = 0.0213°
$$

We can find other calculation that help us ensure users can comfortably read the text on our site

* **Readable for all** x-height for reading efficency is 9 arc min
* **Perfect vision** ideal x-height for reading is 6 arc min
* **Accessible** ideal x-height for reading is up to 12 arc min

After we choose the x-height arc size that meets our expectations, in this case im going to choose 9 to perform calculations

$$
9 / aspectRatio = idealFontArcSize
$$

or we can transform this to use reference pixel units using

$$
9 / 1.2789 = referencePixel
$$

and therefore

$$
7 / aspectRatio = idealFontReferencePixelHeight
$$

![](/assets/images/UI/convergence-ideal-font-size.png){max-width: 400px}

**You can also perform calculations between multiple typefaces to figure out which font size to use in each of them to get a similar perception**

$$
firstFontSize * firstAspectRatio = firstxHeight
$$

then 

$$ 
\frac {firstxHeight}{secondAspectRatio} = secondFontSize
$$


![](/assets/images/UI/concert-one-size-based-on-convergence.png){max-width: 600px}

But this is also not a rule of thumb so feel free to accommodate the font sizes as needed if you feel they dont match 

![](/assets/images/UI/concert-one-size-comparison.png){max-width: 600px}

>Note: If you are using modern web development tools you can use the css property "font-size-adjust" with the value of the first font, and "font-size" with the value of the size font you are using for the first fond to make the second fond accomodate to roughly look like the first font on that size

## Large Text

Readability isn't our concer with these bits of text which means we dont have to follow the 9 arc min x-height, **we want this texts to be attention grabbing and easy to spot, they need to have impact and set the tone**

Some other things we might want to take into account depending on which media we are aiming for

* **Far Away** Screens further away are proportionally bigger
* **Close up** the closer something is to our face the less of our field of vision we want it to take up
* **Billboard** massive ratio between heading and body text

There is another concept we can understand when using arc minutes, if your eyes are positioned in the middle of the screen you have more arc minutes there than you have on the edges of the screen

We have "lens distortion" on our eyes, **imagine our range of vision as a circle around us, because most of the things are made of straight lines it appears to us that things bulge outwards**, to account for this distortion we see things like the Parthenon with no straight lines, the first typefaces accounted for different optical weight depending on the letters size

This distortion is more prominent in bigger things, which means is easier to spot it on our titles, **to account for this we can use heading typefaces with lower optic weighting**

## Line Lenght

We measure line lenght in **characters per line (including spaces)**, some state that 50-75 characters per line is ideal, although we will use this more as a guide than as a rule, specially because this study was made before digital monitors

**For digital monitors some studies have shown that the optimal lenght for readability is 95 characters per line**

But before changing every design ever made `think about the user experience`, less characters may make the user feel like they are going faster and give them ultimately a more pleasant experience

**There is no rule on the optimal characters for optimal user experience so we are basically back to square one, look at what others are doing** 

* **45 - 75** characters per line for latin alphabets
* **15 - 40** characters per line for other alphabets like japanese or chinese

Over time people are becoming more used to reading larger lines so we can lean towards the end of the spectrum following

* **~75 cpl** for computer monitors
* **~60 cpl** for tablets
* **~45 cpl** for mobile

## Line Height

Also know as leading, **is the vertical space between lines of text**. We must choose and line height similar to what most websites use, and we need this similarity because of how we read

When reading we make saccadic eye movements where our eyes jump from one spot to the next reading 3-4 words at a time, **to make reading efficient we have to know where to jump next taking into account the line height**, line lenght and font size, saccadic movements are easier when jumping in a straight line, which means is easier to read a full line than jumping to the next specially if one of 3 sizes mentioned before are not standard

Using **line heights different from the standard can confuse the reader an prompt them to over jump**, the standard is  `line height should be between 130% to 150% of the text height`

$$
Line Height = fontSize * 1.4
$$

![](/assets/images/UI/convergence-ideal-line-height.png){max-width: 400px}

We can also **increase the line height up to 150% to 170% if our font aspect ratio is larger than usual** to make it less dense

> But as all the other recommendations this is just a guideline, if something outside of the standards works well then use it

## Localization

Our latin alphabet is used in many languages so make sure to understand the rules of the language you are using

* **English and spanish** are always read left to right
* Arabic are always read right to left
* **Chinese and Japanese** alphabets have way to complicated glyphs so is common to bump up the size 15%
* We can use css **line-break: strict to avoid part of a syllable breaking over the next line**, while line-break:loose does the opposite
* **South east Asian languages** like thai dont have spaces in between words but rather in between sentences
* **Korean** each symbol is a syllable but each part of the symbol is a phonetic sound so the fonts maybe have each separate phonetic sound or each syllable which can be tricky

**Use UTF unicode to learn more about the specifics of each language**





