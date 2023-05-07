---
id: yvvq8u946xhn7tmwmig4llh
title: Chapter3
desc: ''
updated: 1668550970101
created: 1666279594664
---

# If it's annoying it's probably not accessible

An annoyance is something that causes irritation in some sort of way

## The Annoyances and Solutions

* Pages take too long to load
* Poor functionality of desktop site
* App leads to web site
* Links going to different places/dead links
* Poor content layout
* Pop-ups
* Icons not clear
* FONTS ALL CAPS
* Too much text
* Text spans the full width
* Misplaced button boxes
* AutoPlay

### A page taking too long to load

In the 21st century and there is an expectation that when we visit a page, we 
will be able to view it right away

Even if its imposible to render the page right away there should be some sort of indicator that the page is loading, for sighted users it is easy to indicate with a loading animation but for blind users we need some other sort of indicator

A good indicator could be an alert role, we can use this to indicate screen readers of any kind of warning

```html
<h2 role="alert">Your form could not be submitted because of 3 
validation errors.</h2>
```

### Poor content layout

Usually due to out-of-place hierarchy, we need a proper hierarchy to allow the user to scan the page in a logical way

Content layout is in relation to the WCAG 2.1 success criterion 1.3.1, 
1.3.2, and 1.3.3

* **Success Criterion 1.3.1 Info and Relationships (Level A)**: Information, structure, and relationships conveyed through presentation can be programmatically determined or are available in text.

* **Success Criterion 1.3.2 Meaningful Sequence (Level A)**: When the sequence in which content is presented affects its meaning, a correct reading 
sequence can be programmatically determined.

* **Success Criterion 1.3.3 Sensory Characteristics 
(Level A)**: Instructions provided for understanding 
and operating content do not rely solely on sensory 
characteristics of components such as shape, color, 
size, visual location, orientation, or sound

### Popups

Popups or modals are an annoyance because they stop the user from doing whatever they are about to do. One of the most annoying experience for users is not being able to close modals 

How to improve this experience?

* Make sure you give the user the oportunity to close a popup
* Use proper color constrast to distinguish between the background and the foreground


### Too much text

It might overwhelm the user, also people with dyslexia might have a harder time distinguishing between the letters 

* Break the content into different pages
* Use readable fonts, avoid fonts with too many decorations or fonts with cursive letter
* Build readable layouts
* Use complete sentences
* Use proper contrast between the letters and the background, even if you can see it be aware of others capabilities like color blindness

### Uncertainty related to buttons and links

The user must be able to distinguish between them, if they can not set them appart it can get annoying, remember its not only important to disthinguish their style but also be able to distinguish them for blind users

WCAG SC 1.3.5, 1.3.6, and 
2.2.6 cover this. 

* **SC 1.3.5 Identify Input Purpose (AA)**: For content 
created with markup languages, the purpose of 
specific input fields indicated in WCAG 2.1 needs to be communicated programmatically such as via 
the autocomplete attribute in HTML. The purpose 
can then be transformed by personalization tools to 
communicate this in different ways such as via icons 
or symbols to assist users with cognitive and learning 
disabilities.

* **SC 1.3.6 Identify Purpose (AAA)**: This builds on SC 
1.3.5 and includes communicating purpose for icons, regions, links, buttons, and other user interface elements, to support personalization for people with cognitive and learning disabilities.

* **SC 2.2.6 Timeouts (AAA)**: When a timeout is used, 
advise users of the duration of inactivity that will 
cause the timeout and result in loss of data. Users with 
cognitive disabilities or other focus/memory-related 
disabilities may require more time to read content or 
to complete interactions, such as completing an order 
form. The use of timed events can present barriers for 
people who need to take breaks. Providing the duration 
of inactivity before a timeout occurs will help users 
plan for breaks

### Autoplay

Its not only a weird functionality in itself why would a user want videos to randomly start playing whe scrolling? but its also annoying and dangerous

Videos and flashes can trigger seizures in individuals as well as cause panic 
and anxiety when sound is suddenly blared loudly

There are ways to show the content you want, while allowing the user 
to have control.

* Add a play/stop button to allow the user to have control
* If you must have autoplay, have the video only play once
* Refrain from using audio and opt to have captions with 
transcripts available

### Manipulative (DARK) patterns

They are meant to manipulate the user into doing something he doesnt want to or isnt intending to do

ABC Science case study, CAPTCHA security tests can take in to accountance various things in order to set users appart from computer systems and IA but it also has an incredible flaw, what about a blind user or users with visual impaired?

This made dark patterns extend to unhospitable design features arising from inattention, neglect, and false assumptions about the capabilities and desires of disabled people.

Usually time limits are also a dark pattern for people with disabilities

**WTF - what is the focus?** It could be use to guide the user around the page or to mislead the user into clicking something he is not trying to

### What to do next?

Web accessibility should be part of any project from the ground up, and any accessibility errors should be treted like fire code violations, and should be corrected every time, an remember always take into account the actual user feedback dont rely on tools

### Closing thoughts

* Clear calls to action: differentiate buttons and links
* Clear layout: Create the most logical layout for the individual user of the site
* Typography: use typography that is readable instead of visually appealing
* Ability to apply filters: Allow individuals to control 
filters on the site.
* Clear navigation: Provide clear navigation so the 
individual knows where to go next.
* Appropriate related content: Ensure content is 
connected through the layout.
* Skip to content: Allow users to “skip to content” (this is 
especially helpful for screen readers).
* Correct contrast: Use color contrast checker to validate 
colors are within the guidelines.


