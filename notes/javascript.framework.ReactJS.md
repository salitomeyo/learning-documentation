---
id: 5nut8vglf3v5x9f79nu8xfl
title: ReactJS
desc: ''
updated: 1662728922078
created: 1662153455916
---

This page will contain al the concepts learnt while watching the [**React: De cero a experto ( Hooks y MERN )**](https://udemy.com/course/react-cero-experto) *Udemy course*

## Que es React?

Es una libreria de Javascript, es declarativa (permite crear interfaces de usuario interactivas) y eficiente, trabaja de forma predecible, toda la informacion fluye por una sola via y esta basado en componentes

### Que es JSX

Es simplemente la unicion de JS con XML

## Que es un componente?

Es una pequeña pieza de codigo encapsulada re-utilizable que puede tener o no estado

En las aplicaciones de react se crean arboles de componentes, los componentes pueden estar contenidos y contener otros

## Como crear una app de react

Anteriormente era muy comun utilizar

```bash
npx create-react-app nombre
```

Pero el la version 19 de react se modificaron varias dependencias por lo que las aplicaciones creadas con create-react-app estan siendo deprecadas (tienen un uso de dependencias excesivo que provoca grandes cargas al servidor y los procesos utilizados no estan optimizados para la ultima version)

A causa de esto surgio una nueva forma de inicializar que esta tomando fuerza, esta utiliza `Vite` en lugar de `Webpack`. Ademas usa menos dependencias y esta mucho mejor optimizada para las ultimas versiones de react

```bash
npm create vite
```

### Que es un fragmento?

Un agrupador de elementos de html que nos permite devolver varias etiquetas en un componente de react sin crear elementos extra, es decir no cambia la estructura del html final ya que no agrega nada

```html
<>
    <h1>Salome</h1>
    <p>I'm learning react</p>
</>
```

### Donde definir variables

React propone unas reglas para definir variables, si una variable no tiene relacion con una funcion o es fija lo mejor es definirla fuera del scop del componente, ya que react no va a rerenderizarlas por lo que disminuye el tiempo y poder de procesamiento

```javascript
// Solo se renderiza una vez
const atributoEstatico = 'Salome';
const funcionEstatica = () => {
    return Math.random();
}

export const FirstApp = () => {
    // Se rerenderiza
    const atributoDependiente = 'Oe';

    return (
        <>
            ...
        </>
    )
}
```

### Que son props

Son atributos que se pueden enviar a cualquier componente definido en react, permiten la comunicacion entre componentes

#### prop-types

Es una libreria que nos permite controlar el tipo de los props enviados a un componente, esto puede servir especialmente para dar a conocer a otros desarrolladores posibles errores en el uso de estos parametros 

```bash
npm install prop-types
```

Tambien podemos definir los valores por defecto de los props (hasta incluir props que no fueron enviados al componente)

```javascript
FirstApp.propTypes = {
    title: PropTypes.string.isRequired,
    subTitle: PropTypes.number
}

FirstApp.defaultProps = {
    title: 'No hay titulo',
    cat: 'Jade',
}
```

## Mapeo de listas a componentes

React tiene una forma muy simple de convertir cada uno de los objetos de una lista o arreglo en su propio objeto, para esto debemos utilizar la funcion map la cual mapea cada componente de un arreglo a cualquier etiqueta html que usemos

```javascript
{ categories.map( category => {
    return <li key={ category }>{category}</li>
}) }
```

Una caracteristica de react es que la opcion map siempre debe contener un indice (key) y un valor, en el caso anterior utilizamos el mismo nombre de la categoria como key, pero tambien podemos utilizar **indices autogenerados**, para usarlos basta con poner 

```javascript
{ categories.map( (category, index) => {
    return <li key={ index }>{category}</li>
}) }
```

>Nota: Aunque usar indices autogenerados puede parecer una solucion rapida a varios inconvenientes en realidad react considera esto una mala practica por lo que debemos evitar utilizarlos tanto como sea posible

## Desestructuracion

Usualmente cuando queremos desestructurar objetos utilizamos la desestructuracion de javascript, y aunque esta es una opcion util y es una buena practica react nos otorga una forma incluso mas sencilla de desestructurar objetos, imaginemos el siguiente componente que recibe un titulo y una url

```javascript
export const GifGridItem = ({ title, url }) => {
    return (
        <div>
            algo
        </div>
    )
}
```

En primera instancia podemos pensar que para mandar estos argumentos debemos de hacer la separacion manualmente

```html
<GifGridItem 
    key={objeto.id}
    title={objeto.title} 
    url={objeto.url} 
/>
```

Pero en realidad hay una forma mucho mas sencilla que nos permite mantener un codigo mas limpio, y significa exactamente lo mismo

```html
<GifGridItem 
    key={objeto.id}  
    { ...objeto }
/>
```

Al utilizar `...objeto` lo que estamos haciendo es pasando cada uno de los atributos desestructurados al componente

>Usar `...objeto` es especialmente util cuando un objeto tiene demasiados atributos

