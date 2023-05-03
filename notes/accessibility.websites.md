---
id: 91g6ax7jj50sqif5fvi3cm5
title: Websites
desc: ''
updated: 1672688108153
created: 1672260985739
---

# How to create accessible websites

## What is semantic html?

Using the elements you're meant to use, the appropiate elements carry meaning and importance that its helpful for different users, specially ones that have visual difficulties

* Headers actually have importance and give the page an order, H1 must appear only once per web page and should be located at the start of the page
* We must always take into account the semantic meaning behind the tags but we can also change the meaning using attributes

### Colors

**1 in 200 women are colorblind and so are 1 in 12 men**, there are some colors that are hard to distinguish but usually there are colors they can see, is a misconception thinking every person with colorblindness cant see colors at all, but in any case color must not tranfer meaning

Dont rely on colors for distinghising things between one another, for example

* in a shop page dont use only color swatches but use also text
* In a login form if there is a mistake or something like that make sure to tell the user with words not only turning the input box red

Make sure to use a contrast checker before submitting to a color scheme or make sure the font is big enough to be disthingishable even if the colors are similar

* Dont make hover only change color, user border for example
* Create mockups in gray scale

>Note: Is better to use outline than border because the border actually moves the content around

### ARIA

Aria are other kind of common attributes that can help us make the websites more accessible, they help us add meaning to the elements

**`aria-label`**: We can use it to add descriptions to things that are not visible to users, for example, a link that only has icons cant be understand by a screen reader, we can explain its function using aria-label

```html
    <a href="www.instagram.com">
        <svg aria-label="Follow company on instagram"></svg>
    </a>
```

When an aria-label is used in a button assistive technologies will only read the content inside the label and not the content other users can see

**`aria-labelledby`**: We can use it to add descriptions in elements that are bound to change, for example instead of renaming an images everytime it changes we can just link the aria-label to some other element by the id and make it automatically change 

```html
    <img src="images/munckhin.png" 
        alt=""
        aria-labelledby="caption"
    >
    <p id="caption">Munckhin Cat</p>
```

**`role`**: Change the semantic meaning of the tag used to the tag asigned inside the role attribute for example

```html
    <a role="button">Click me!</a>
```

**`tabindex`**: We can add this attribute to any element to make it interactive, this means when someone is accessing our page via keyboard the tab button will make this element a focusable one inside the tab tree and it will be selected once all the other elements with tabindex are accessed

```html
    <img src="images/munckhin.png" 
        tabindex="0"
    >
```

This should only be used for elements that are interactive, text and other can be read with a screen reader without having the tab index attribute

>Note: Interactive elements have the tabindex="0" built-in so they will always be inside the tab tree, if you want to deactivate an element front the tab tree then use tabindex="-1"

**`aria-hidden`**: We can use it to hide an element from assistive techologies but it will still be visible for all the other users

**`aria-current`**: is a way to give feedback to a screen reader user to know where they are currently located, for example in the home page, is the equivalent of having an active styles differentiator

```html
    <nav>
        <a href="/" aria-current="page">Home</a>
    </nav>
```

**`aria-expanded`**. It helps users using screen reader to figure out if a button its actually a collapsible button, for example a menu, and it also shows the user the current state of the collapsible. Make sure to change the value with js

```html
    <nav>
        <button aria-expanded="true">Menu</button>
    </nav>
```

### Images

Images is one of the most commonly used visual elements that can be quite confusing and difficult for users with visual difficulties or even bad connections, we need to make sure that even without looking at the images our websites are fully readable and understandable

**`alt`**: Use to place a short description of the images for users that are not able to see them or when the images dont render, they should always be used

```html
    <img src="img/flowers.png" 
        alt="Field of pink flowers"
    />
```

>Note: its unnecesary to put "image of" in the alt because screen readers will say "image" reading the img tag

If you are using an image as a link is better to describe where the link leads to than describe the image

If the image contains text you must write the whole text in the alt attribute 

### Outline

Outlines are a great way to show focus and possible interactivity for some users, for examples users with low contrast vision dant usually see the element they are targetting because the style changes is not clear enough

Outlines help break the pattern of using color as the only distingishable point and they are much more eaasy to spot for some users, dont rely on the built in outlines because they are too subtle

### Bypass Blocks

Are skip links that pop up on the screen when accessing it through a keyboard in order to help keyboard users go the the main or most common element in the page (for example a download button) without having to travel through the whole page in order to reach a certain content

This bypass are usually hidden and only pop up when a user starts using the keyboard in a page, this can be done using simple css setting the position outside of the page with some indextab element and then changing the position of the element to appear on the top of the screen when on focus

### Accessible videos and audios

We must have captions for every video or audio content we have on our page, there are two types of captions open and closed

* **Open**: There are embeded into the video and cant be turned off nor be edited, the advantage of this is that they can be seen by any player even if it doesnt support captions
* **Closed**: They can be turned on and off, can be presented in different languages and can be easily edited if a mistake was made, but you need a player that supports this capabilities

Quality captions include:

* Correct grammar & punctuation
* All on-screen text, e.g. if the speaker is showing something written in a book or a sign and doesn't say it
* Audio description e.g. "chimes", "monitor beeping erratically", "door hisses open"
* Placement that doesn't block important things on the screen (e.g. the speaker's face)

This not only helps people with hearing problems or also help people traveling or in noisy environments to be able to enjoy audible sources, we can also include transcripts and even better if they are interactive

Remember not to autoplay and take into account possible animations that can induce seizures

### Iframes

Embeded maps like google maps iframe cant be read with a screen reader, so we must make the iframe as descriptive as possible

* We must use the title attribute to describe what the iframe is used for and which content its showing

The best option for maps is to actually write the direction in text format outside the iframe 

### Forms

Using placeholders as labels is a common practice but its really not accessible for screen readers users, the best way to create forms is using labels with empty placeholder and no values (the input boxes should be empty, we can use other labels or paragraphs to indicate users the type of input we are specting)

If you cant use the required value for any particular reason you can use the 

**`aria-required`**: This will indicated screen reader users that a input is mandatory

Instead of using buttons that just say "Submit" try to describe what the button actually does, for example "Send message"

If you are using the common * to indicate users something is required than make sure this sign is hidden for screen readers

```html
<form>
    <label> 
        Your name <span aria-hidden="true" style="color: red;">*</span>
        <input class="form-control" id="name" required />
    </label>
</form>
```

Another thing to take into account is describing the rules or special characters and their meaning even if they are of common usage, this will help users with learning disabilities and other user that may not have the context required to understand certain indicators like elder users

For example you can write "All fields marked with an asterik ( * ) are required"

### Icons

Icons usually have 2 meanings they are either used for decorations purposes or to show a common brand or social media 

* **Decorative icons**: If the icons serve no other purpose but to look pretty but they add no aditional meaning, then make sure to hide them for screen readers users specially if the icons are svg because the scrre reader may start reading the path properties

* **Brands, social media and other icons**: use aria-label to describe the name of the social media and what the purpose of the button or link does, for example "Follow our company on Instagram"

### Links

Its better to never use links that redirect the user to another window because this might confuse screen readers and keyboard users but if its absolutely necesary to open a link in a new window make sure the user is aware of this either using an aria-label or a aria-describedby 

```html
    <a href="instagram.com" aria-label="Follow our company on instagram (opens in new window)"><span class="fa fa-instagram"></span></a>
```

Images asociated to links should describe what the link is for instead of what the image is showing

Finally links should have a descriptive enough information on their own, dont use links that only have words like "click here!" because they dont tell users navigating the page with the tabindex tree what the link is for because they dont actually access the text before it, instead make the button content descriptive

**Bad example**
```html
    <p> Looking for the best vet service?, to make an appointment 
        <button> Click here! </button>
    </p>
```

**Recommended**
```html
    <p> Looking for the best vet service?,  
        <button> Make an appointment! </button>
    </p>
```

