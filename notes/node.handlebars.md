---
id: 2s8oux7tpioezifanoghmeh
title: Handlebars
desc: ''
updated: 1662751159279
created: 1662748792505
---

Es un package de npm que nos permite tener unas funcionalidades extra en html por ejemplo para trabajar con variables dentro del codigo html

Aunque este paquete en realidad **no es muy potente su uso para proyectos grandes no es recomendado** para acceder a documentacion mas precisa acerca del mismo referirse a la [documentacion oficial](https://www.npmjs.com/package/handlebars)

```bash
npm i handlebars
```

Este es el package general para trabajar con handlebars vanilla, pero handlebars tambien tiene multiples versiones dependiendo del framework utilizado

>Nota: Handlebars usa el patron mbc, que nos permite separar la vista, el codigo y el controlador

# HBS

Es la version de handlebars para trabajar con Express, para informacion mas detallada hacerca del mismo referirse a la [documentacion oficial](https://github.com/pillarjs/hbs)

```bash
npm i hbs
```

## Como usar

Una vez instalado debemos indicar a express que queremos renderizar el codigo a traves de hbs, para esto 

```js
app.set('view engine', 'hbs');
```

Una vez instalado he importado podemos reemplazar los archivos html en la carpeta public por archivos `.hbs` en una carpeta llamada views alojada en el root del proyecto

Y para renderizar estos archivos podemos usar el siguiente llamado

```js
app.get('/', (req, res) => {
    res.render('home');
})
```

El nombre dentro del .render() debe corresponder al nombre de cada archivo .hbs

Inside the render we can also send a second argument, this will be all the parameters that we can call inside the hbs files

```js
app.get('/', (req, res) => {
    res.render('home', {
        name: 'Salome Aristizabal',
        title: 'Node Udemy Course'
    });
})
```

And inside the hbs file to refer to any of the send parameters we just have to use `{{ parameterName }}`

### Partials

HBS tambien nos permite reutilizar codigo lo cual es muy util cuando estamos trabajando en html puro y no tenemos acceso a componentes, para esto utilizamos parciales

Para utilizar parciales debemos importar hbs y registrarlos

```js
const hbs = require('hbs');

hbs.registerPartials(__dirname + '/views/partials', function (err) {});
```

Dentro de la carpeta views/partials podemos crear nuestros nuevos archivos partials que se pueden entender como componentes, usualmente se usan para definir codigo que se repite en multiples pantallas como el navbar o el footer

El nombre de estos partials es muy importante ya que asi nos referiremos a estos en los demas archivos .hbs

Por ejemplo en el archivo `navbar.hbs` podriamos tener el siguiente bloque de codigo html 

>Nota: No se necesita usar todo el formato de archivos html en los partials, basta con guardar el snippet del codigo

```html
<nav id="menu">
	<ul class="links">
		<li><a href="index">Home</a></li>
		<li><a href="generic">Generic</a></li>
		<li><a href="elements">Elements</a></li>
	</ul>
</nav>
```

Posteriormente para utilizar este partial en cualquier otro archivo hbs basta con usar 

```js
{{> navbar}}
```
