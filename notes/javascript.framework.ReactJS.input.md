---
id: 5gyehdfqh10le991e46ztj6
title: input
desc: ''
updated: 1662727923315
created: 1662475494506
---


Al trabajar con inputs es necesario realizar todas las funcionalidades inherentes del mismo, es decir necesitamos:

1. Almacenar el valor del input
2. Detectar los cambios
3. Modificar el valor del input
4. Enviar el valor del input cuando se hace un submit

Todas estas funcionalidades es necesario implementarlas constantemente, por esto se realizara una pequeña guia de como hacer un input

## 1. Almacenar el valor del input

En primera instancia debemos crear el input con que vamos a trabajar

```html
<input 
    type="text"
    placeholder="Search gifs" 
/>
```

El input original no requiere ninguna clase de parametro especial pero esto solo nos otorgara la visual del mismo, no tendra funcionalidad, por esto requerimos en:

* Crear una variable que almacenara el valor del input para esto usaremos el useState

```javascript
const [ inputValue, setInputValue ] = useState('');
```

* Posteriormente debemos asignar el valor de esta variable al input, para esto existe la propiedad value

```html
<input 
    type="text"
    placeholder="Search gifs"
    value={ inputValue } 
/>
```

## 2. Detectar los cambios

Al realizar los pasos anteriores el input esta conectado a una variable pero es inmutable, asi que debemos de realizar el siguiente proceso para tener en cuenta los cambios del usuario

Existe una propiedad en los inputs que se encarga de manejar estos cambios llamada onChange

```javascript
<input 
    type="text"
    placeholder="Search gifs" 
    value={ inputValue }   
    onChange = { (event) => onInputChange(event) }
/>
```

Esta propiedad debe llamar una funcion que se encarge de actualizar el valor de la variable, cabe destacar que la funcion que se llama en la propiedad **onChange en la mayoria de ocasiones debe recibir el evento**, el evento se llamara cada que realiza un cambio en el input y guarda un monton de informacion acerca del mismo

>Nota: Es indiferente si la propiedad onChange se llama en su version mas extensa con proposito ilustrativo
`onChange = { (event) => onInputChange(event) }` o en su version mas breve, la cual es mas utilizada en entornos de produccion ya que permite una visualizacion de codigo mas limpio `onChange = { onInputChange }` con ambas se obtiene exactamente el mismo resultado y significan lo mismo

## 3. Modificar el valor del input

Una vez sabemos que funcion vamos a llamar en el onChange es necesario crear esta funcion, esta funcion recibira el event pero en realidad solo necesitamos su atributo target por eso realizamos la desestructuracion del mismo

```javascript
const onInputChange = ({ target }) => {
        setInputValue( target.value );
    }
```

Esta funcion se encarga de modificar la variable inputValue conforme cambia el valor del input de forma que se mantenga la cohesion entre los mismos

## 4. Enviar el valor del input cuando se hace un submit

Finalmente para enviar el valor del input cuando se hace submit hay muchas formas diferentes pero una de las mas utilizadas consta de embeer los inputs en una etiqueta form que se encarge de manejar este evento

```javascript
<form onSubmit={ (event) => onSubmit(event) }>
    <input 
        type="text"
        placeholder="Search gifs" 
        value={ inputValue } onChange = { (event) => onInputChange(event) }
    />
</form>
```

Y para definir que realiza la funcion onSubmit en este caso vamos a realizar un envio del parametro del inputValue por los props, es decir le queremos enviar el valor final del value al componente padre donde se este llamando este componente hijo, esto no es estrictamente necesario pero en este caso lo usaremos asi 

```javascript
const onSubmit = ( event ) => {
    event.preventDefault();
    if( inputValue.trim().length <= 1 ) return;
    onNewCategory( inputValue.trim() );
    setInputValue('');
}
```

`event.preventDefault();` Se encarga de **evitar que la pagina se recarge** cuando se hace un submit, le dice a la pagina que no es necesario hacer un rerender

`if( inputValue.trim().length <= 1 ) return;` Se encarga de hacer una **comprobacion sencilla**, si el input tiene menos de un caracter no realiza el envio, esto no es necesario pero es un ejemplo de como se pueden realizar comprobaciones de los valores del input

`onNewCategory( inputValue.trim() );` Este es el **prop** que recibe nuestro componente, es decir lo usaremos como nuestro **camino de comunicacion con el padre** ya que el es el que va a manejar la informacion del input, si la informacion del input se manejara dentro del componente esto seria innecesario y se podria reemplazar con cualquier otro procesamiento de datos

`setInputValue('');` Reestablecemos el valor del input a un string vacio esto no es necesario pero en este caso lo necesitamos, ademas es una buena practicar para darle feedback visual al usuario de que el formulario fue enviado correctamente

# Ejemplo

Aqui se mostrara el codigo final de ambos archivos para no dejar paso a dudas, el archivo padre tendra 

```javascript
import { useState } from "react";
import { AddCategory } from "../components/AddCategory";

export const GifExpertApp = () => {
    const [categories, setCategories] = useState(['One Punch', 'Dragon Ball']);

    const onAddCategory = ( newCategory ) => {
        setCategories( [newCategory, ...categories] )
    }

    return (
        <>
            <AddCategory
                onNewCategory={ onAddCategory }
            />
        </>
    )
}
```

El archivo hijo que se encargara de todo lo relacionado al input tendra 

```javascript
import { useState } from "react"

export const AddCategory = ({ onNewCategory }) => {
    const [ inputValue, setInputValue ] = useState('');

    const onInputChange = ({ target }) => {
        setInputValue( target.value );
    }

    const onSubmit = ( event ) => {
        event.preventDefault();
        if( inputValue.trim().length <= 1 ) return;
        onNewCategory( inputValue.trim() );
        setInputValue('');
    }

    return(
        <form onSubmit={ (event) => onSubmit(event) }>
            <input 
                type="text"
                placeholder="Search gifs" 
                value={ inputValue }   
                onChange = { (event) => onInputChange(event) }
            />
        </form>
    )
}
```



