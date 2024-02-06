---
id: hnhwauyqd3nryi64ziz6oj8
title: Inquirer
desc: ''
updated: 1662728980950
created: 1661864375625
---

Inquirer es un package de npm que nos permite **usar una consola de comandos interactiva** mas facilmente y a su vez nos permite manejar diferentes tipos de interacciones que pueden ser tediosas al crearlas desde 0

## Como instalar

Como es un package de npm se puede consultar toda la informacion sobre el mismo en [Inquirer](https://www.npmjs.com/package/inquirer) pero basta con usar el comando

```bash
npm i inquirer
```

## Como usar

Las ultimas versiones de inquirer ya no permiten la importacion usando require, por lo que es necesario hacer unas modificaciones antes de poder utilizarlo en un proyecto

1. En el `package.json` es necesario agregar 

```javascript
"type": "module",
```

2. Si el proyecto estaba usando importanciones tipo require es necesario reemplazarlas todas por `import` y adicionalmente agregar la importacion de inquirer

```javascript
import inquirer from 'inquirer';
```

3. Finalmente es necesario modificar todos los exports que siguieran el patron `module.export`, por

```javascript
export{}
```

## Funcionalidades

Inquirer tiene varias funcionalidades, para informacion mas detallada acerca de las mismas referirse a lo documentacion oficial, pero en este documento se detallaran un poco las funcionalidades que a mi criterio han sido mas utiles

### Notas generales

`name:'nombre'` es el nombre del atributo que retornara este llamado, este es el valor que debemos tener en cuenta a la hora de desestructurar el return

`type: 'tipo'` Se encarga de definit las funcionalidades en consola que se tendran, es importante siempre asegurarse que este corresponda a las funcionalidades que queremos

### Option

Esta funcionalidad nos permite crear menus interactivos con diferentes opciones, para movernos entre estas opciones podemos utilizar las flechas del teclado y para seleccionar una opcion basta con darle enter

```javascript
const options = [
    {
        type: 'list',
        name:'option',
        message: 'Message the user will see in console',
        choices: [
            {
                value: '1',
                name: '1. Option',
            },
            {
                value: '2',
                name: '2. Option',
            }
        ]
    }
]
```

Para definir uno de estos menus es importante recordar que el `type: 'list'`

Las **choices se refieren a todas las opciones del menu** y pueden ser tantas como se desee, el valor que se retornara al programa sera el correspondiente al `value` y lo que el usuario podra ver en consola sera correspondiente al `name`

Para indicarle a inquirer que utilice este menu debemos usar, el return correspondra al value de la opcion escogida por el usuario

```javascript
const { option } = await inquirer.prompt(options);

return option;
```

### Input

El input nos permite esperar en consola un input del usuario y devolverlo, cabe destacar que se debe asegurar `type: 'input'`

```javascript
const question = [
    {
        type: 'input',
        name: 'description',
        message,
        validate( value ){
            if ( value.length === 0 ) {
                return 'Por favor ingrese un valor';
            }
            return true;
        }
    }
]
```

El `message` corresponde al input del usuario, este valor es siempre necesario al utilizar el type input

>Nota: la opcion `validate` no es obligatoria pero nos permite realizar cualquier tipo de validacion en la entrada antes del envio de los datos, en caso de que no se necesite ninguna validacion basta con borrarla

Finalmente para utilizarlo al igual que en cualquier otra funcionalidad de inquirer basta con invocarlo usando 

```javascript
const { description } = await inquirer.prompt(question);

return description;
```

### Checkbox

Los checkbox permiten al usuario escoger varias o todas las opciones de un menu (a diferencia del option que solo permite escoger una opcion), cabe destacar que se debe asegurar `type: 'checkbox'`

```javascript
{
    type: 'checkbox',
    name:'ids',
    message: 'Selecciones',
    choices
}
```
En este caso el return sera una lista que contenga cada uno de los valores de las choices escogidas por el usuario

### Confirm

Este tipo sirve para confirmar un input del usuario, por defecto contiene el return de true (Y) pero el usuario puede denegarlo con tan solo enviar (n) correspondiente a false, se debe asegurar el `type: 'confirm'`

```javascript
const question = [
    {
        type: 'confirm',
        name: 'ok',
        message
    }
]
```


