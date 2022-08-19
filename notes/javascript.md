---
id: 9nyv2jnm266u99zyw1vautw
title: JavaScript
desc: ''
updated: 1660950382659
created: 1660598968195
---
This page will contain al the concepts learnt while watching the [**JavaScript Moderno: Guía para dominar el lenguaje**](https://www.udemy.com/course/javascript-fernando-herrera/) *Udemy course*

## Usos de javascript

Surgio con la necesidad de enviar al servidor la informacion de la forma mas procesada posible

1. Aplicaciones web
2. Crear presentaciones
3. Web servers (with nodeJS)
4. Videogames
5. Aplicaciones (ionic, React Native)

## Definiciones clave

**Metodo**: es una funcion dentro de un objeto, cualquier invocacion a una funcion que contenga la sintaxis

>objeto.funcion() 

En realidad hace referencia a un metodo de ese objeto

**Node**: Nos permite correr javascript fuera de la web

**Comentarios**: Son lineas de codigo que el interprete de javascript va a ignorar

**Variable**: Es un contenedor de informacion que apunta a un lugar en memoria

>Se pueden definir como `let` o `var` aunque ahora usar var no es una buena practica ya que es una implementacion antigua y podria no ser soportada en algunos navegadores

Las variables **var** se escriben en el objeto global window, este es otro motivo por el que var se considera mala practica, lo que significa que una variable tipo var que posea el mismo nombre que una variable global del window puede ser sobreescrita usando var lo cual es muy peligroso y dificil de detectar 

Las variables tipo var tambien pueden permitir su llamado antes de inicializacion retornando undefined

**Constante**: Es una variable cuyo valor no puede cambiar, el valor con que se define originalmente es fijo

**Polyfill**: Es un codigo que provee el funcionamiento de una nueva caracteristica de JavaScript en versiones viejas como ES5

### Que version de java usar

* **ES5**: Es soportada en todos los navegadores
* **ES6, ES7, ES8**: Soportada por la mayoria de navegadores modernos pero pierde compatibilidad con navegadores antiguos, pero pueden ser implementadas con POLYFILL

### Sintaxis

>Javascript **ignora todos los espacios y tabulaciones** por lo que la identacion del codigo la puede definir el programador a su preferencia

* **Variables globales**: Se acostumbra utilizar nombres completamente en mayusculas cuando

* **global**: Es un objeto que solo funciona en una consola al invocar node, este objeto no puede ser usado en la web, del mismo modo los metodos tipo `alert, prompt, confirm` no estan definidos al ejecutar el codigo en la consola pero si funcionan en un navegador web

* **Debilmente tipado**: No hay que especificar el tipo de dato

* **Primitivos**: Es una informacion que no es un objeto y es inmutable, hay 6 tipos de primitivos en javascript

    * Boolean
    * Null - Sin valor
    * Undefined - Variable declarada que aun no se le asigna valor
    * Number
    * String
    * Symbol - Valor unico 


* **Camel Case**: Se acostumbra nombrar las variables usando camel case

* **Palabras Reservadas**: Son palabras que tienen un uso especifico, y no deberian usarse para un proposito diferente al que ya tienen asignado

>Se puede verificar que un nombre pertenece a una palabra reservada o podria generar error usando [Validador de nombres](https://mothereff.in/js-variables#%E0%B2%A0%5f%E0%B2%A0)

### Tipos de datos

* **Arreglos**: Son un objeto muy parecido a una lista de informacion, contiene un grupo de elementos, usualmente contienen el mismo tipo de dato

* **Objetos**: Cualquier dato que no sea de tipo primitivo en javascript es un objeto, 

* **Objetos literales**: Son objetos que tienen pares de valores

>Para conocer mas informacion acerca de los objetos de javascript [Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

### Funciones

Su objetivo principal es **centralizar la logica de un procedimiento** que se va a ejecutar varias veces

Cualquier funcion de javascript que no tenga un return explicito devuelve *undefined*

Hay 3 clases de funciones que pueden en javascript:

* Default functions
* Anonymous functions
* Arrow functions

### Referencias

Todos los **`primitivos son pasados por valor`**, es decir la modificacion de uno no modificara el otro en ningun caso

```cmd
let a = 10, b = a;
a = 30;

console.log({ a, b }) //30, 10
```


Todos los **`objetos son pasados por referencia`**, es decir la modificacion de uno de ellos modifica a todos los que esten apuntando a este 

```cmd
let juan = { nombre: 'Juan' }, ana = juan;
ana.nombre = 'Ana';

console.log({ juan, ana }) //{nombre: 'Ana'}, {nombre: 'Ana'}
```

Para evitar pasar objetos a traves de referencias utilizamos la variable **spread**, esto rompe las referencias y pasa cada parametro por separado

```cmd
let juan = { nombre: 'Juan' }, ana = {...juan};
ana.nombre = 'Ana';

console.log({ juan, ana }) //{nombre: 'Juan'}, {nombre: 'Ana'}
```

### Estructuras de control

Permiten configurar la linealidad con la que el interprete ejecuta el codigo escrito en javascript

#### Nota

La diferencia entre **==** y **===**

* **==** significa que verifica los datos comparados sean iguales pero no importa el tipo de dato

```cmd
let a = 5;
return a == '5'; //true
return a == 5; //true
```

* **===** verifica que los datos comparados sean iguales y que su typeof tambien sea igual

```cmd
let a = 5;
return a === '5'; //false
return a === 5; //true
```

### Operadores logicos 

Los operadores logicos como 

<table>
    <thead>
        <tr>
            <th>Operador</th>
            <th>Simbolo</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>NOT</td>
            <td>!</td>
        </tr>
        <tr>
            <td>AND</td>
            <td>&&</td>
        </tr>
        <tr>
            <td>OR</td>
            <td>||</td>
        </tr>
    </tbody>
</table>
</br>

Solo se ejecutan hasta que se cumple la condicion o hasta donde se decida que es imposible de cumplir


<details>
<summary><b>Por ejemplo</b></summary>
<p>Supongamos que tenemos las siguientes funciones</p>

```cmd
const returnTrue = () => {
    console.log('true');
    return true;
}

const returnFalse = () => {
    console.log('false');
    return false;
}
```

* Si usamos un **&&** y una condicion es false ya no seguira ejecutando las demas condiciones, es decir:

```cmd
const a = returnFalse && returnTrue;
```

Solo imprimira por consola 'false' porque nunca llamara la funcion returnTrue

* Si usamos un **||** y una condicion es true ya no seguira ejecutando las demas condiciones, es decir:

```cmd
const a = returnTrue || returnFalse;
```

Solo imprimira por consola 'true' porque nunca llamara la funcion returnFalse

</details>

#### Operador ternario

Es una forma resumida de escribir un condicional if-else en una sola linea, esto se considera una buena practica y una forma de mantener clean code

La sintaxis del mismo es

const variable = ( `condicion` ) ? [**true**]:[**false**];

> const tipoDia = ( [0,6].includes(dia) ) ? 'Fin de semana' : 'Semana';

### Ciclos

Los ciclos permiten realizar instrucciones de codigo varias veces

Existen 2 ciclos importantes:

* For
* While

#### Ciclos For

Hay 3 clases diferentes de ciclos for en Javascript

##### For 
El for por defecto **utiliza un contador**, una restriccion para detenerse y un incrementador

```cmd
for(let i = 0; i <= 2; i++){}
```

##### For in
El for in sirve para **recorrer listas** y arreglos **usando indices** del mismo

```cmd
for(let i in lista){ lista[i] }
```

##### For of
El for of sirve para **recorrer listas** y arreglos pero en este caso **usando los elementos**

```cmd
for(let elemento of lista){ elemento }
```

### Patron modulo

Nos sirve para encapsular el codigo y protegerlo de forma que no quede todo definido en el objeto global window, esto dificulta ataques e invocaciones de terceros.

Pueden ser definidas con funciones flecha

```cmd
(() => {
    ...codigo
})();
```

O con funciones por defecto

```cmd
(function() {
    ...codigo
})();
```

Este patron hace uso de **funciones anonimas para ocultar bloques de codigo del entorno global**

>Para saber mas acerca de funciones anonimas autoinvocadas referirse a la nota

<details>
<summary>Mas sobre las funciones</summary>

Las funciones anonimas pueden ser definidas de 2 formas

* Funcion anonima comun

```cmd
() => {
    ...codigo
};
```

* Funcion anonima autoinvocada

```cmd
(() => {
    ...codigo
})();
```

**Nota**: Estas funciones tambien permiten la utilizacion de un modo de codigo estricto, el cual habilita varias restricciones lo cual ayuda a que el codigo generado sea mas limpio y mejor estructurado

Para usarlo basta con agregar **'use strict'** a la definicion de la funcion

```cmd
(() => {
    'use strict'
    ...codigo
})();
```

</details>

### Minify

Se recomienda siempre usar archivos de javascript minificados a la hora de enviar a produccion, ya que esto tambien va a añadir una capa extra de seguridad al codigo

Para minificar javascript hay varias opciones pero dejo una de ellas 

[Minify JS](https://www.toptal.com/developers/javascript-minifier)
