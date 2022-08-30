---
id: 9hd0s7mwp6uwrp05db74ftn
title: Promises
desc: ''
updated: 1661547189807
created: 1660925638869
---

## Callback

Es simplemente una **funcion que se llama como argumento** y va a ser ejecutada posteriormente. Estos permite manejar diferentes respuestas y errores

Era muy comun utilizarla antes de que se crearan las promesas pero ahora se considera una mala practica ya que facilmente puede provocar un callback hell

Los callbacks funcionan de forma sincrona lo que significa que hasta que no se resuelvan pueden bloquear la ejecucion del programa

### Callback hell

Es un code smell que surge al utilizar callbacks ya que cada callback a una funcion puede ser anidado dentro del callback anterior y se genera una recurrencia muy dificil de controlar

## Promise

A diferencia de los callbacks las promesas son asincronas lo que significa que el programa puede seguir ejecutandose sin necesidad de esperar la respuesta del callback

Las promesas tambien permiten manejar errores y respuestas, ademas tienen varias funcionalidades ya implementadas para evitar el callback hell que se presentaba anteriormente

### Promise All

Recibe varias promesas y no ejecuta el codigo hasta que todas las promesas se hayan resuelto

```cmd
Promise.all([ promesa, promesa ]).then( arr => {
    console.log('promesas resueltas')
})
```

Adicionalmente podemos agregar un catch que se encargara de manejar cualquier tipo de error que resulte al llamar las promesas, si una promesa resulta en un error las demas promesas del promise.all ya no se ejecutaran

```cmd
Promise.all([ promesa, promesa ]).then( arr => {
    console.log('promesas resueltas');
}).catch( err => {
    alert(err);
})
```

Finalmente podemos agregar un finally que se ejecutar al finalizar una promesa independientemente de si resulto en error o no

```cmd
Promise.all([ promesa, promesa ]).then( arr => {
    console.log('promesas resueltas');
}).catch( err => {
    alert(err);
}).finally(() => {
    console.log('Promise.all ended');
})
```

### Promise race

Solo ejecuta la promesa que se ejecute mas rapido, incluso si las promesas mas lentas resultan en error esto no va a activar el catch

```cmd
Promise.race([ promise, promise ])
.then( console.log )
.catch( console.warn );
```


### Async-Await

Las funciones async await permiten manejar las promesas de una forma mas simple ya que no resulta necesario definir el resolve y el reject, sino que estos ya estan implementados y solo debemos usarlos, esto resulta en un codigo mas limpio

* Sin usar async-await

```cmd
export const searchHero = ( id ) => {
    const hero = heroes[id];

    return new Promise( ( res, reject ) => {
        if ( hero ) {
            res( hero );
        } else {
            reject( `There is no hero with the ${ id } id` );
        }
    });
}
```

* Usando async-await
```cmd
export const searchHeroAsync = async ( id ) => {
    const hero = heroes[id];

    if ( hero ) {
        return hero;
    } else {
        throw `There is no hero with the ${ id } id`;
    }
}
```

Como se puede ver no es necesario crear la nueva promesa para manejar el resolver y el reject cuando usamos async await

>Se recomienda nunca utilizar await dentro de un ciclo for de promesas ya que esto impedira que se ejecuten de forma asincrona e incrementara exponencialmente el tiempo de ejecucion 

### Try-Catch

Los bloques try catch permiten controlar errores, el codigo dentro del try se intentara ejecutar y si resulta en cualquier clase de error se ejecutara el codigo dentro del catch

```cmd
try{
    console.log('Do something');
} catch ( err ) {
    throw err
}
```

