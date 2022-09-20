---
id: dirl4j8penvhjnc1hu7de8l
title: hooks
desc: ''
updated: 1663359417916
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

### Recomendacion

React recomienda que en lugar de hacer pocos useEffect con muchas funcionalidades es preferible hacer muchos useEffect especificos con responsabilidades unicas

Para controlar esto correctamente se recomienda usar la siguiente estructura en los useEffect

```js
useEffect(() => {

        return () => { 

        }
    }, [])
```

Antes del return usamos todas las funcionalidades necesarias, y dentro del return detenemos todos los llamados a funciones innecesarias para evitar consumo extra de memoria 

## useRef

Nos permite mantener una referencia y cuando esa referencia cambia no se dispare una rerenderizacion del componente

Usualmente se utiliza para hacer focus a algun elemento en particular usando una referencia al mismo

## useMemo

Nos permite modificar la ejecucion de funciones de forma que solo se ejecuten cuando se cumpla una condicion independientemente de si el componente se ha rerenderizado o no

Por ejemplo es muy utilizado para el llamado a funciones que reciben un parametro, para llamar estas funciones solo si el parametro cambia

```js
import { useMemo, useState } from "react";
import { useCounter } from "../hooks/useCounter"
import { Small } from "./components/Small";

const heavyStuff = ( iterationNumber = 20 ) => {
    for( let i = 0; i < iterationNumber; i++ ){
        console.log('Iterating...');
    }

    return `${ iterationNumber } iterations done!`
}

export const MemoHook = () => {
    const { counter, increment } = useCounter( 10 );
    const [ show, setShow ] = useState( false );
    
    const memorizedValue = useMemo( () => heavyStuff( counter ), [counter] );

    return(
        <>
            <h1>Counter: <Small value={counter} /></h1>
            <hr />

            <h4>{ memorizedValue }</h4>

            <button
                className="btn btn-primary"
                onClick={increment}
            >
                +1
            </button>
            <button
                className="btn btn-outline-primary"
                onClick={() => setShow( !show )}
            >
                Show/Hide { JSON.stringify(show) }
            </button>
        </>
    )
}

```

En este ejemplo solo se hace llamado a heavyStuff cuando el valor del counter cambia, pero cuando el boton setShow cambia no se ejecuta el heavyStuff aunque el componente se rerenderize

## useCallback

Nos permite guardar una funcion para evitar que se cambie su referencia cada vez que un componente se rerenderiza

Por ejemplo veamos el siguiente ejemplo utilizando memo

```js
export const Hijo = memo(({ incrementar }) => {

    console.log('  Me volví a generar :c  ');

    return (
        <button
            className="btn btn-primary"
            onClick={ () => incrementar() }
        >
            +1
        </button>
    )
})
```

Utilizamos memo para **almacenar un componente** hijo, este componente no se volvera a renderizar cuando su padre cambie a menos que el cambio lo afecte directamente, el problema en este caso es que el componente recibe una funcion y cada vez que se rerenderiza el componente padre la referencia a la funcion cambia por lo que a esto genera una rerenderizacion del hijo y el uso de memo pierde su proposito

```js
import { Hijo } from './Hijo'
import { useState, useCallback } from 'react';

export const Padre = () => {
    const [valor, setValor] = useState(0);

    const incrementar = useCallback(
        () => {
            setValor( ( oldValue ) => oldValue + 1 );
        },
        []
    )

    return (
        <div>
            <h1>Padre</h1>
            <p> Total: { valor } </p>

            <hr />

            <Hijo 
                incrementar={ incrementar }
            />
        </div>
    )
}
```

Pero si la funcion que le enviamos al componente hijo es una funcion definida con useCallback entonces el componente hijo no se rerenderizara porque la referencia a esta funcion sera la misma siempre 

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

