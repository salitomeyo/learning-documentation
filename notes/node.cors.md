---
id: uld2m2yb78iua8r1filwowx
title: Cors
desc: ''
updated: 1662758206702
created: 1662756838059
---

Es un package de npm que nos permite proteger nuestros servidores, aunque de una forma relativamente superficial, para tener mas informacion al respecto referirse a la [documentacion oficial](https://www.npmjs.com/package/cors)

## Instalacion

Basta con ejecutar el siguiente comando 

```bash
npm i cors
```

## Como usar

Cabe resaltar que para usar el package de cors tenemos que estar utilizando express, una vez express este funcionando podemos importar cors utilizando 

```js
var cors = require('cors');
```

Posteriormente debemos indicar a express que utilizaremos cors, esto usalmente se puede realizar como un middleware

```js 
app.use(cors());
```

Cors nos permite crear whitelist que son los dominios con permiso de realizar peticiones a nuestro webserver y blacklist que son los permisos que tienen prohibido realizar peticiones a nuestro webserver