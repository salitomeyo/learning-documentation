---
id: yv3vt9yjs58hfu944zkwok2
title: reducer
desc: ''
updated: 1663361405911
created: 1663360809356
---

Un reducer tiene 4 caracteristicas principales:

1. Un reducer es una funcion comun y corriente
2. Debe de ser una funcion pura (es decir todo lo que se realice debe suceder dentro de la funcion), es decir:
    * No debe tener efectos secundarios (no debe de llamar otras funciones)
    * No debe de realizar tareas asincronas
    * No debe de llamar el localStorage ni el sessionStorage
    * No debe requerir mas de una accion para modificar el state, la accion puede tener o no argumentos
3. Debe de retornar un nuevo estado
4. Usualmente recibe 2 argumentos
    * El valor inicial (initialState)
    * La accion a ejecutar

## Porque?

Sirven para tener controlado en un solo lugar todas las acciones que alteran los state o estados de la aplicacion

## Ciclo de vida

El state envia su informacion para ser renderizado en la vista, pero la vista no habla directamente con el state sino que crea una nueva accion, esta accion es la que se envia al reducer y el reducer es el que se encarga de las modificaciones del state y de mantener los planos de todas las acciones que se pueden ejecutar 

