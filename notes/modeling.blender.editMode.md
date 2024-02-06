---
id: e5wrz9ns46sl1g7maoa6khv
title: Edit Mode
desc: ''
updated: 1681179364140
created: 1681053404799
---

Inside the modeling window we can find the edit mode which is a mode that allows us to modify vertex, edges and faces.

This is used when you wish to achieve a more polish and blocky appareance (you will not be able to easily achieve natural looking objects and shapes as in sculpting mode) buts its good for low-poly and overall linear shapes like weapons, houses, etc

## Submenus

* **Ctrl + V**: Will enter the submenu with all the possible transformations you can apply to vertexes in general, if you have a vertex or a group of vertex selected it will turn the menu into a context menu which has a lot more options
* **Ctrl + E**: Will enter the submenu with all the possible transformations you can apply to edges in general, if you have an edge or a group of edges selected it will turn the menu into a context menu which has a lot more options
* **Ctrl + F**: Will enter the submenu with all the possible transformations you can apply to faces in general, if you have a face or a group of faces selected it will turn the menu into a context menu which has a lot more options
* **Right-Click**: We can also right click will having an vertex, edge or face selcted and it will open the corresponding menu
* **Alt + E**: Will enter the extrude submenu

## Triangulation

Blender divides objects in triangles, which means any object no matter how many vertex it has is being broken into triangles by blender internal processing, this triangles will have a specific direction that cant be modied unless we actually triangulate our object 

* **Ctrl + T**: Triangulate the selected object or face, which mean it will turn every face into a triangle
* **Alt + J**: Detriangulate which turns a previusly trianguled object into its original form without triangles
* **Rotate edge**: Right-click in a selected edge and use ´Rotate edge CW´ Which rotates the direction of the edge 

## Editing

* **J**: while selecting two vertices to create a edge between them
* **Shift + A**: Lets us add new geometries to our currect object, this will not create new elements inside our collection 
* **Ctrl + P**: It let us parent different geometries
* **Snap**: It fixes our possible moves and modifications to the grid, we can activate it inside the edit mode area in the middle top part selecting the magnet icon
* **Pivot point**: This will be center point our modifications will be applied from, we can change it to 3D cursor, median point, individual elementes, etc depending what we want to achieve in the edi mode area in the middle top part at the left of the magnet icon
* **V**: While selecting a vertex to split the vertex in two

## Selecting

* **A**: Select all
* **Alt + A**: Deselect all 
* **Shift + Left-Click**: Select various vertices, edges or faces 
* **Ctrl + I**: Inverse select, select all the vertices, edges or faces that werent selected and unselect the ones that were
* **Ctrl + Left-Click**: Selects the shortest path between to vertices, edges or faces
* **Shift + Ctrl + Left-Click**: selects all the vertices, edges or faces in a plane between two or more previusly selected 
* **L**: Select linked
* **B**: Select box, creates a dragable box we can use to select anything the box touches
* **C**: Select circle, creates a circle pointer that can be increased or decreased using the mouse wheel, just keep the left-clicked pressed till you selected everything
* **Ctrl + B**: Deselect box, creates a dragable box we can use to deselect anything the box touches
* **Ctrl + C**: Deselect circle, creates a circle pointer that can be increased or decreased using the mouse wheel, just keep the left-clicked pressed till you deselected everything
* **Ctrl + Change selection mode**: Lets us keep the selection made in the current selection mode and translate it to other modes
* **Left-Click + Left-Click**: Select a loop around the objects that includes the current edge, vertex or face
* **Shift + Left-Click**: Select a loop around the objects that includes the current edge, vertex or face
* **Ctrl + Shift + Left-Click**: Select a loop of vertices or edges that are positioned as the current edge, vertex or face, this vertex are not connected are just equivalent

### Grouping

We can enter the object data properties (the green graph in the properties window) and create vertex groups with the vertices currently selected

We can use this when we have a selection that we need to use many times in case we are afraid to lose the selection

* **Assing**: We use this to add the current selection to the saved group
* **Remove**: We use this to deselect the current selection to the saved group
* **Select**: We use this to select the selection in the chosen group
* **Deselect**: To invert the selction in the chosen group

### Special selections

We can use the select menu in the top of the edit mode area to expand the submenu with all the posible selections

* **Checkered deselect**: To deselect every other vertex, edge or face in the current selection, specially useful on loop selections, we can change the offset and the skip patron if we want to skip more than one element at a time
* **Select random**: Randomly select some vertices, edges or faces in the current object, the percentage of selected elements can be ajusted as well as the seed
* **Select mirror**: We can select the exact same items we are selecting now but in the oposite side of our object, we can also change the axis, and if we want to keep our current selection we can choose extend
* **Select side of active**: We previously have to have one vertex selected, this will be the middle of the sides created, we can change the axis and the sign, which will change us between one side and the other
* **Select more/less**: it increases or decreases our selection (its keymap by default to Ctrl + Numpad- and Ctrl + Numpad+ but i changed it) `Ctrl + WheelUp` and `Ctrl + WheelDown`
* **Select linked flat faces**: it selects every face that has the same angle as the one currently selected, it can basically select any plane `Ctrl + L`, but the angle of threshold can also be changed

### Other selections

* **Alt + B**: Select and hide everything outside the selection, to return back to normal view we just have to click Alt + B again
* **Select all by trait**: it can help us find orphan vertices, edges and faces that are separated from the principal geometry, we can also choose by sides and select all the faces that match the number of vertices chosen
* **Shift + G**: It displays a submenu that lets us select similar things to our currently selected

## Deleting

* **X**: Delete menu, it show us all the possible things and forms we can delete our current selection
    * **Vertices, Edges and faces**: Will delete all the vertices, edges or faces currently inside the selection
    * **Disolve**: This will fill out the disolved vertices, edges and faces with the ones around it 
    * **Limited Disolve**: this will only disolve things that fit in a certain treshhold angle, this will keep the shape as it is but will delete meaningless divisions, for example a subdivided plane can be turned back into a single faced plane. If we select all boundaries it will ignore holes and reshape the object more abruptly
    * **Edge collapse**: Will turn and edge into a vertex in the middle of the chosen edge
* **Ctrl + X**: it will work the same as a disolve depending on what you have selected either vertices, edges or faces

> Note: if we delete the whole object inside the edit mode we wont delete it from the collection, we will just create an empty object

## Mesh

* **M**: Mesh menu it allows us to easily access collapse options 
    * **At center**: It works the same as edge collapse
    * **At cursor**: It collapses the selected into a vertex located in the same position as the 3D cursor
    * **By distance**: Its only shown when selecting vertices, it merges vertices that fit in a certain treshhold distance from each other

## Subdivisions

* **Ctrl + R**: We can use this in any cylinder type form to create a new loop, we can use the mouse will to increase the number of loops made
* **Edge subdivide**: Sometimes when we want to use ctrl+r to other forms like cones we wont be able to get it working, if this happen just select all the edges where you want the loop to sit, then Right-Click and choose subdivide, this will have the exact same effect

## Marking

* **Mark sharp**: We use it when we are using smooth shanding in our object but we want some of the edges to remain sharp, with the edges selected Right-Click and choose Mark sharp

## Overlays

When we are seeing a object in studio lighting we might not realize problems like the normals of the object being inside out, when we 

* **Change the lighting**: Top right corner in the edit area, `shading` dropdown to other lightings and materials like matcap

We can find that our objects is shade diferently than before, this could mean a problem in the normals direction, to be sure of this we can 

* **Activate face orientation**: Top right area in the edit area `overlay` dropdown, when we activate it we will see every objct in our scene in either blue or red, if the color of the object is red it means its normals are pointing towards the inside of the object which is a problem for lighting and others

But we can easily fix this

* **Changing normals direction**: Inside object mode select the object you need to change the normal direction, enter edit mode, use `A` to select the object, and click `Shift + N`, it usually recalculates it automatically but if you run into a problem just expand the menu and manually select the direction



