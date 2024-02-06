---
id: yqcpj8ga737geihk03ze6mq
title: Building Our Grid
desc: ''
updated: 1704927178724
created: 1688650175676
---

## Align to Grid

When adding elements to your grid is important to take into account **you can not align elements to the outside of your regions but to the inside**, which means if you cant go over the vertical regions to use the gutters

You either have to realign the element to fit on the colum before the gutter, or you have to fit your content in both columns, **basically you can only use the gutters as design space for an element if the element is using the columns around it**

Another uncommon but acceptable use is to **overlap elements in between regions**, imagine you are using a 3 column grid, with an image and a title, the title can go over the image and share the second column space

Is usually fine for icons to overlap a little over the boundaries instead of perfectly fit into them

## Embeded Grid

We can use different grid systems for different parts of out page, for example one for the header and one for the body

One of the tips people use to keep things interesting is create the grid and regions and then expand the elements on the page across different regions

Other way to break the simmetry while keeping the order is to use embeded grids, **any region inside of a grid can contain its on inside grid, the new grid doesnt have to relate in any way but mantain a sense in uniformity because they use the same (or similar enough) gutter and margin width**

## Building our Grid

Developers will always make some design decisions because **not everything can be fully translatable to code but we want to minimize how many decisions the developer needs to make**, here are some pointers to help you achieve this

* Some design softwares dont allow float numbers so **is usually easier to round your desing up and then tell the developer the actual sizes** that they should be using
* You can **create a new grid thr size of any of the multiples of your original grid** after deciding the typography as it makes it easier for you to arrange larger elements
* You **will have tons of different grids, make sure to use different layers on each one** to avoid creating confusions and making the grids unintelligible
* To facilitate grid creation on different elements on figma its recomended to **use components**
* Having a responsive grid can make alignment really hard so **dont be bother by little missalignments**

### How to make our grid more responsive

The recommendation is to create 3 different designs those designs will be invariable (fluid but the main design will remain unchanged) in their pixel range but will switch to another design when the pixels no longer match the range

* Desktop: 1200px - 1600px
* Tablet: 1200px - 900px
* Mobile: 900px - 600px

This break points could change if needed but maintaining this consistency will facilitate developers work









