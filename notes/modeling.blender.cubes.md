---
id: okwxjrokp65q10du607sc2r
title: Cubes
desc: ''
updated: 1681074799185
created: 1679857558533
---

We can easily create structured objects using cubes, some of the most useful shortcuts are

## Modifier

* **Bevel**: We can use this to create a little rounded border, some good presets are Amount: 0.016, Segments: 4

> **Reapply modifier to diferent objects:** We can apply the same modifier to multiple objects by selecting all the objects and using `copy to selected`

* **Mirror**: Make sure you use a mirror object that wont be moved around until the mirror is applied

* **Change modifier values in multiple objects**: We can hold `alt` to change values in a modifier while having multiple objects selected with the same modifier to apply the changes to all of them 

## Combining objects

* **Ctrl + A**: We use this in order to reset the rotation and scale values in order to avoid problems later

* **Ctrl + J**: We use this in order to combine all the objects currently selected into one big object, its harder to modify the object after combined so `make sure you do all the modifications before combining`

## Changing pivot 

Sometime when combining object we can find the pivot of the combined object is set in a weird place, but we can always change it using the 3D cursor

First make sure you put the 3D cursor in the exact place you want the cursor, it can be really hard to place it by hand so some steps to make it easier and more acurrate are

* **Modeling mode**: We need to enter modeling mode while having the object we want to change the pivot

* **Select vertex or edge**: Make sure the selection mode aligns to the place you want the pivot to be, if you select a vertex it will be set in the exact vertex position, if its a edge it will be set in the middle of the edge

* **Set 3D cursor**: Once you have selected the place you want the pivot to be use the top tool bar, select `Mesh > Snap > Cursor to selected`

* **Layout mode**: When the 3D cursor is correctly set go back to layout mode

* **Set Pivot**: Once in layout mode use the top tool bar, select `Object > Set origin > Origin to 3D cursor`

## Separating combined objects

We need to choose the object previously combined and separate it, take into acoount that we dont have to separate all the objects componing our joined object, we can just separate a single part

* **Vertex and edges view**: First we choose the object we want to separate, then we pressed `Tab` in order to enter the vertex and edges view of our object

* **Select part**: We can choose any of the vertex in the object part we want to separate and then use `L` to autoselect the whole object

* **Separate**: Once we have selected the whole object we want to separate we use `P` and select `Separate selection`

* **Normal view**: We can use `Tab` again in order to return to the normal view

This will divide that specific part from the object but the rest of the object will remain intact



