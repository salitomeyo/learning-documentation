---
id: 0uijwgomah05m44assl0qce
title: testing
desc: ''
updated: 1662728940500
created: 1662396062650
---

# JEST

Las pruebas se dividen en 2 grandes grupos

* Unitarias: Enfocadas en pequeñas funcionalidades

* Integracion: Enfocadas en como reaccionan varias piezas en conjunto

## Caracteristicas de las pruebas

* Faciles de escribir
* Faciles de leer
* Confiables
* Rapidas 
* Principalmente unitarias

## AAA

### Arrange

Se encarga de la inicializacion de variables y las importaciones

### Act

Se encarga de la aplicacion de acciones o estimulos, se llaman los metodos, se simulan clicks, se realizan acciones sobre arrange

### Assert

Se encarga de observar el comportamiento resultante y contrastarlo con los resultados esperados

## JEST

Es una de las herramientas de testing mas utilizadas para los proyectos de react y en general muchos frameworks de javascript

```bash
npm install --save-dev jest
```

Se deben realizar algunas modificaciones una vez instalado, para mas informacion visitar la [documentacion oficial de jest](https://jestjs.io/docs/getting-started)

### @types/jest

Es una dependencia de desarrollo que ayuda a que el editor de codigo muestre las recomendaciones de comandos de jest, es muy util a la hora de programar

```bash
npm install --save-dev @types/jest
```

## Trabajando con promesas

Para testear funciones que devuelven promesas es necesario esperar a que la promesa se resuelve, hay una forma sencilla de indicarle a jest que debe esperar la resolucion de una promesa, basta con recibir el parametro `done` dentro del test 

Y luego volver a invocarlo donde se resuelve la promesa

```javascript
test('funcionConAsync debe de retornar algo en una promesa', ( done ) => {
        funcionConAsync( )
            .then( algo => {
                expect(algo).toBe('whatever');
                done();
            });
    })
```

# React Testing Library

Es otra herramienta de testing que tambien es muy popular en las aplicaciones de react, a diferencia de la creencia general tanto la libreria de Jest como la de React testing library se pueden usar simultaneamente y es una buena estrategia ya que cada una de ellas tiene sus ventajas

* Es muy util para la manipulacion del DOM, incluso jest recomienda hacer estas manipulaciones con otra herramienta ya que no es el fuerte de jest

```bash
npm install --save-dev @testing-library/react
```

Para poder implementar esta libreria con jest debemos instalar otras dependencias y configurar algunos archivos

## Archivos de configuracion

En primera instancia debemos crear el archivo **babel.config.js**

```javascript
module.exports = {
    presets: [
        ['@babel/preset-env', {targets: {esmodules: true}}],
        ['@babel/preset-react', {targets: {runtime: 'automatic'}}],
    ],
};
```

Igualmente debemos crear el archivo jest.config.js

```javascript
module.exports = {
    testEnvironment: 'jest-environment-jsdom'
}
```

>Si surge un error con estos archivos basta con cambiar la extension de estos archivos de .js a .cjs

## Dependencias

Debemos importar algunas dependencias para poder trabajar correctamente con estas herramientas de testing, aunque pueden parecer muchas importaciones en realidad solo debemos importarlas en modo dev, lo que significa que al hacer un build estas dependencias no seran utilizadas 

* @babel/core 
* @babel/preset-env
* @babel/preset-react
* babel-jest
* jest-environment-jsdom

