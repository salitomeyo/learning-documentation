---
id: dirl4j8penvhjnc1hu7de8l
title: hooks
desc: ''
updated: 1662727795634
created: 1662488358651
---

Los hooks le dicen a una aplicacion de React que su estado cambio, por ende hay que volver a renderizar la misma, esto puede parecer un proceso tedioso pero react ya lo tiene muy optimizado

## useState

`useState` es uno de los hooks mas utilizados en react, este nos permite facilmente utilizar constantes para almacenar valores y cambios

Cabe destacar que como se utilizan constantes estas no pueden ser reasignadas, por eso siempre que usamos useState debemos definir tanto la constante como su modificador, esto nos permitira cambiar el valor de la constante en el codigo

```javascript
const [ counter, setCounter ] = useState( 0 );
```

Como se puede observar dento del llamado a useState definimos el valor original, y el modificador se define con la palabra especial set

>Aunque no es necesario poner el set se considera una buena practica por lo que siempre se utiliza

## useEffect

Hacer el llamado de una funcion dentro de el scope de un componente es una muy mala practica ya que esa funcion va a rerenderizarse y reejecutarse con cada modificacion al componente, este consume muchos recurso y adicionalmente es muy poco efectivo

Por esto se creo el hook useEffect que sirve para **disparar la ejecucion de efectos secundarios**, es decir un efecto que queremos disparar cuando algo suceda, lo que nos permite controlar cuando se ejecutan estos efectos 

```javascript
useEffect( () => {
    getGifsByName( category );
}, [ ])
```

El primer argumento del useEffect contiene las funciones que se van a llamar o los efectos, en este caso nuestro efecto es `getGifsByName( category );`, y en el segundo argumento se definen las condiciones para que se ejecuten estos efectos, en este caso nosotros tenemos una condicion vacia `[ ]`, lo que significa que este efecto solo se llamara la primera vez que se ejecute el render, todas los demas rerenderizados no haran el llamado de estos efectos

## Custom Hooks

Cuando queremos crear nuestro custom hook react siempre recomienda acogerse al estandar de los hooks, es decir usar siempre el prefijo use

Para crear uno de estos custom hooks basta con crear un componente funcional con el nombre que deseemos, esto permitira escribir logica que se repita en archivos comunes y que pueda ser reutilizada en varios componentes indiferentemente

```javascript
import { useState } from "react"

export const useFetchGifs = ( category ) => {
    const [ gifs, setGifs ] = useState([]);
    const [ isLoading, setIsLoading ] = useState( true );
    
    return {
        gifs,
        isLoading
    }
}
```

Estos hooks pueden contener logica del mismo modo que cualquier otro componente, ademas dentro de ellos podemos utilizar cualquier otro hook ya definido, y para utilizarlos basta con invocarlo como cualquier otro hook de react

```javascript
const { gifs, isLoading } = useFetchGifs( category );
```

