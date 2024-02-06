---
id: 9ztj4rdbq417zun7rxxp5sd
title: Yargs
desc: ''
updated: 1662729006843
created: 1661708053160
---

Yargs es un package de npm que nos permite **manipular los comandos de ejecucion** mas facilmente y a su vez nos permite **crear nuestros propios comandos** y argumentos personalizados

## Como instalar

Como es un package de npm se puede consultar toda la informacion sobre el mismo en [Yargs](https://www.npmjs.com/package/yargs) pero basta con usar el comando

```bash
npm i yargs
```

## Como usar

Una vez instalado tendremos acceso a un nuevo comando que nos ayudara a mantener control de los comandos creados.

>Nota: Para crear nuevos comandos y tener control sobre los argumentos enviados en la linea de comandos debemos agregar unos metodos y propiedades a la importacion de yargs

#### .ARGV

Al usar .argv se **almacenaran todos los argumentos enviados** al correr el programa en la constante argv

```javascript
const argv = require('yargs').argv;
```

#### .OPTION

Podemos agregar atributos adicionales a la importacion para **crear un nuevo comando personalizado usando**

```javascript
const argv = require('yargs')
    .option('b', {
        alias: 'base',
        type: 'number',
    })
    .argv;

```

Cada uno de los .option creado corresponde a un comando personalizado que aparecera al usar --help

Una vez tenemos definidos los atributos podemos agregar diferentes propiedades a los mismos, tales como valor por defecto, si el atributo es requerido o no, condicionales, entre muchos otros

#### --HELP

El help **devuelve una lista de todos los comandos actualmente definidos en el proyecto**

```bash
node nombreArchivo --help
```


