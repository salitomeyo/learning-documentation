---
id: pbvab1jyd8t72q1g3qjyj5t
title: TypeScript
desc: ''
updated: 1662728954344
created: 1662153413873
---


## Typescript

Surgio como un superset del lenguaje de Javascript con la intencion de solucionar algunas de las problematicas que se identificaban y dificultaban el uso de js como un lenguaje robusto

Typescript soluciono

* Tipado de variables
* Errores en tiempo de escritura (linter)
* Auto completado
* Clases y modulos (ES6)
* Validacion de objetos dentro de objetos
* Tipado de respuestas http

Los **navegadores no entienden ni compilan en typescript, typescript es transpilado a javascript**, lo que significa que a la hora de ejecutarse se traduce a javascript y se ejecuta el codigo en javascript

## Como transpilar typescript

Si typescript fue instalado de manera global basta con utilizar 

```bash
tsc
```

De lo contrario debemos crear una configuracion para el transpilador de typescript usando el archivo tsconfig.json

Para no tener que transpilar los archivos cada vez podemos usar un **watcher de typescript** que a cualquier cambio en un archivo typescript va automaticamente a traspilar a javascript

## Tipos de datos

Typescript al ser un **superset** de javascript permite la utilizacion de todos los tipos de datos de javascript, adicionalmente añade otros

* Crear nuevos tipos
* Interfaces
* Genericos
* Tuplas

### Constantes

Cuando usamos constantes en typescript sin especificar el tipo de variable, typescript crea un nuevo tipo para la constante a la que le asigna el valor de la misma

Es decir 

```typescript
const a = 10; //type 10
const a: number = 10; //type number
```

>Se recomienda siempre especificar el tipo de variable de las constantes cuando se usa typescript

Para que se active el error de que una variable no fue declarada su tipo podemos utilizar la regla `"noImplicitAny": true` dentro del tsconfig

Especificar los tipos tambien nos permite tener mejores ayudas y evitar casteos confusos

### Never

Es un tipo de dato de typescript que se utiliza para las funciones que no tienen un punto alcanzable, es decir la funcion termina en un error

### Undefined

Por defecto typescript no permite asignar el valor undefined a una variable que no sea tipo undefined. Es decir

```typescript
let a: string = undefined; //no permitido
```

 esto se puede cambiar usando la regla `"strictNullChecks": false` dentro del tsconfig pero no es recomendado, se prefiere especificar la aceptacion de el undefined

 ```typescript
let a: (string|undefined) = undefined; //permitido
```

**En lugar de usar undefined se recomienda usar null** en todos los casos posibles 

### Types

Los tipos son una funcionalidad agregada de typescript que permite crear **plantillas de objetos** para reutilizar en le codigo y permitir un mayor control

Pero estos tipos no son traducidos a js ya que no existe esta funcionalidad

### Interfaces

La unica diferencia entre las interfaces y los tipos es que las **interfaces se pueden extender**, pero en general se pueden usar indiferentemente en muchos de los casos

>Se recomienda no anidar objetos en una interfaz, en su lugar se deberia crear su propia interfaz para cada objeto

Las interfaces al igual que los types no tienen traduccion a js por lo que al transpilar el codigo desaparecen

### Namespaces

Se pueden considerar agrupadores que nos permiten encapsular y proteger el codigo de forma que externo al namespace solo se tenga acceso a lo que ha sido exportado 

## Como depurar codigo TypeScript

**La depuracion en los errores no es muy util en typescript** ya al transpilar el codigo a javascript las estuctura del mismo cambia, por esto la ayudas en consola que exponen **las lineas donde se encontro el error y otras ayudas no se estan refiriendo directamente al archivo de typescript sino al archivo transpilado**

### Como mejorar la depuracion

Podemos agregar configuracion al tsconfig que nos ayuden a detectar los errores directamente en los archivos ts

Para esto debemos activar `"sourceMap": true`

>Esto puede generar mucho codigo basura asi que siempre resulta importante eliminar los archivos mapeados posteriormente 

### Remover los comentarios

Para evitar tener codigo basura y disminuir al maximo el espacio ocupado de los archivos transpilados se recomienda activar la configuracion `"removeComments": true` en el config

### Como ignorar archivos y directorios

Cuando estamos usando un watcher por defecto todos los archivos generados en el proyecto que sean .ts seran automaticamente transpilados a .js

Si queremos evitar que algun directorio genere estos archivos podemos agregarlo a la configuracion usando `"exclude": ["directorio"]`

Esta opcion debe estar por fuera del compilerOptions, es decir

```typescript
"compilerOptions": {
      //rules
    },
    "exclude": [
      "directorio"
    ]
```

Tambien puede suceder del como contrario usando el `"include": ["directorio"]` para indicar que unicamente se deben transpilar todos los archivos de el directorio especificado

Por defecto **node_modules** es excluido en la configuracion de tsconfig

## Salida

Para evitar generar un archivo de js para cada uno de los archivos .ts se debe agregar `"outFile": "./main.js"` a la configuracion, esto creara un unico archivo centralizado que sera la union de todos los archivos ts construidos hasta el momento que esten siendo incluidos

>Al hacer esta centralizacion tambien se recomienda mantener el map para saber la referencia a cada archivo .ts

### Propiedades de un objeto

Si durante una consulta debemos extraer las propiedades de un objeto y pero este **objeto puede retornar undefined** basta con poner `?` antes de llamar a la propiedad, esto significa que solo ejecute el codigo de llamado a la propiedad si la respuesta es diferente de undefined

```typescript
return powers.find( power => power.id === this.powerId )?.description || 'Not found'
```

>Solo si encuentra un poder en powers cuyo id sea igual al powerId llamara a su propiedad `description` de lo contrario retorna 'Not found'

Si por el otro lado tenemos que una funcion puede **retornar undefined pero sabemos que nunca lo hara** y queremos **obligar al llamado de la propiedad** debemos usar `!` esto significa que ignore la advertencia del posible undefined y si o si llame la propiedad 

```typescript
return powers.find( power => power.id === this.powerId )!.description || 'Not found'
```

### Funciones genericas

Las funciones genericas sirven para que el argumento defina su propio tipo independientemente de que argumento entre 

```typescript
function genericFunction<T>( argument: T ) {
    return argument;
}
```

### Quicktype

Si estamos trabajando con peticiones http es comun mapear la respuesta como interface para poder acceder facilmente a sus atributos, pero en ocaciones la respuesta es muy grande y mapear esto a mano se hace tedioso por lo que utilizamos 

* [QuickType](https://quicktype.io/)
* [QuickType-VSCode](https://marketplace.visualstudio.com/items?itemName=quicktype.quicktype)

## Decoradores

Son funciones que se ejecuta en tiempo de transpilacion, permite expandir la funcionalidad de un objeto


