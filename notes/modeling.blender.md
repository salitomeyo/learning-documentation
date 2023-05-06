---
id: cjlwd514b7r72anlsf62kta
title: Blender
desc: ''
updated: 1681175532858
created: 1671494629088
---

## Basic controls

* **Boton central del raton**: Navigate and orbitate 
* **Ctrl + boton central**: Zoom
* **Shift + boton central**: panear
* **Alt + boton central**: Preset view point
* **Ctrl + Alt + Q**: Divides view in 4, one for each axis and one general 3D, if you use this again the view will return back to normal

****

## Work modes

### Object mode

Allows us to create and move objects

Having an object selected we can use the following keyboard shortcuts

#### Change render 

* **Z**: Submenu that allows us to change between different renders posibilities like Solid, Wireframe, Material previews and Rendered to change the way we see our objets
* **Shift + Z**: x-ray vision

#### To move

* **G**: Move object
* **G + X**: Move object in the x edge
* **G + Y**: Move object in the y edge
* **G + Z**: Move object in the z edge
* **G + shift + X**: Move object in every edge but the x
* **G + shift + Y**: Move object in every edge but the y
* **G + shift + Z**: Move object in every edge but the z
* **G + G**: To move vertices along the edges they belong to, and move adges along the faces they belong to but are limited to the size of the edge, which means its good for shrinking but cant make thing bigger than the original size
* **G + G + C**: To move vertices along the edges they belong to, and move adges along the faces they belong with no limitations

#### To rotate

* **R**: Rotate object
* **R + Y**: Rotate object in the y edge
* **R + Z**: Rotate object in the z edge
* **R + X**: Rotate object in the x edge
* **R + shift + X**: Rotate object in every edge but the x
* **R + shift + Y**: Rotate object in every edge but the y
* **R + shift + Z**: Rotate object in every edge but the z
* **.**: Open the submenu of the pivot point we can change the point our rotations are applied from

#### To scale

* **S**: Scale object
* **S + Y**: Scale object in the y edge
* **S + Z**: Scale object in the z edge
* **S + X**: Scale object in the x edge
* **S + shift + X**: Scale object in every edge but the x
* **S + shift + Y**: Scale object in every edge but the y
* **S + shift + Z**: Scale object in every edge but the z
* **Alt + S**: Scale object through normals

#### To Duplicate

* **Ctrl + D**: It allows us to copy and paste the object we currently have selected into the window
* **Ctrl + C**: It allow us to copy the object currently selected and store it in cache, which means we can use this copy even if we close the current window or open a new blender file
* **Ctrl + V**: It allows us to paste the object we currently have stored in the cache
* **Alt + D**: It allows us to copy and paste objects as Ctrl+D but it links the object which means each transformation made to one of the objects will also affect its copy
* **Shift + R**: Repeats last it allows us to duplicate the last paste exactly the same

#### 3D cursor

* **Shift + S**: Displays 3D cursor menu

Its common to move the 3D cursor an then the origin to the 3D cursor position

#### how to create favourites

We can select any command in the menus and right click it to convert it into a favourite

* **Q**: Display the favourites commands menu

#### Other shortcuts

* **Shift + A**: add a new object, mesh where the 3D cursor is currently located
* **N**: opens the transform information menu
* **Ctrl + j**: it lets us combine different transforms in the hierarchy in order to be able to edit them all at once
* **Ctrl + A**: Revert transformations, scale, positiion, rotation

*Numpad*
We can use all the buttons in the numpad to change views

### Edit mode

Allows us to modify objects vertices, edges and faces 

* **E**: Allows us to extrude the face we have currently selected
* **Double-Click**: Allows us to select all the faces or edges that form a closet circuit, for example all the vertical faces in a cylinder
* **Shift + Click**: Allows us to select multiple edges, vertex or faces
* **Ctrl + B**: Apply bevel

### Sculpt mode

Allows us to sculpt objects, it takes in to account the edges and vertex, the more you have the better control over the sculpting tools

#### Creating more vertex

Through the modifiers
> Add modifier > Subdivision surface

The best way to sculpt is having a lot of subdivisions

Through the modifiers
> Add modifier > Multiresolution

it help us mantain different lvls of subdivision in the diferent modes

If we scalate a tranform its common that the sculpt brushes dont work the same way, we can fix this setting the scale of the object in every dimension to 1
> N > scale = 1.0


* **F**: Change the brush size
* **Alt + M**: Eliminates the mask
* **Alt + H**: Eliminates the hide box

#### Faceset

* **H**: Nos permite ocultar las diferentes face set, al usar H sobre un face set oculta todos los face set exceptuando el actual
* **Ctrl**: Permite seleccionar un color de mascara ya creado y seguir usandolo, si no usamos crtl se crea una faceset nuevo

#### Brush properties

To reach the brush properties we have to open the tab **"Tools"** in the right side of the screen

We can change a lot of brush properties to achieve different goals but some of the most useful properties are

* **Front face only**: the brush will only affect the face in direct contact with the brush, its located inside the *advanced* submenu
* **Stabilize stroke**: It shows a guide with the direction of the brush in order facilitate the usage and create cleaner strokes, its located inside the *stroke* submenu

