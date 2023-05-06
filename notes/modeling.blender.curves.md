---
id: yq20nzi1e13zdfsv63a6w3t
title: Curves
desc: ''
updated: 1680147330686
created: 1675020986406
---

We can use curves to easily create hair, the thing is you have to take into account some of the controls will change, for this we will have to create curves called **paths**

## Simple editing

We can simply modify paths usign the following commands and tricks

* **G**: To move any vertice of the curve

### Object data properties

In the object editing menu (the green option) to solidify the shape

* **Bevel - Round**: to create a simple cilinder with the shape of the curve
* **Bevel - Object**: To create a shape matching any other curve object, this tool is really useful with circle curves (Bezier Circles)

### Right click submenu

* **Subdivide**: Creates a new vertice between two selected vertices
* **Set Handle Type**: To Change the tanget of the curve (we can change it to vector to have different tangets on either side of a vertice)


## Modyfing curves

* **shift + S**: To Scale one node (vertice of the curve)
* **Ctrl + T**: To rotate a vertice
* **O**: To scale using smooth curves
* **Ctrl + Shift + B**: To create bevel inside a curve, you need to use the mouse in order to apply it and use the scroll to increase the number of bevels to ensure smoothness

## Filling curves

* **F**: To fill the face combining all the vertex selected
* **Geometry Depth**: We can use the curves properties (green logo in the properties menu) an access the `geometry>Bevel>Profile>Depth` input to fill our curve with a 3d volumen sorrounding it following a chosen curve, we can use `geometry>Bevel>Round>Depth` input to fill our curve with a 3d volumen sorrounding it following a cilindric shape, `geometry>Bevel>Shape>Depth` or input to fill our curve with a 3d volumen sorrounding it following a chosen shape

## Transforming plane to curve

* **Deleting edges**: We can select edges from a plane an eliminate them using the edges delete option on the deleting menu using `X`, when we eliminate edges from a plane we are left with a faceless curve because you can only fill closed curves
* **Deleting faces**: We can select all vertex from a plane using `A` then use `X` and chose delete only faces, this will leave us with only the vertex and edges 
* **Converting to curve**: We need to select the whole plane inside layout mode, `right click` it and chose `Convert to>curve` this way we can use the geometry depth to fill the curve

