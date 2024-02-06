---
id: 245ntrslmvwwud6h1vs2pqa
title: Dotenv
desc: ''
updated: 1662728973388
created: 1662677708699
---

Es un modulo que nos permite manejar facilmente variables de entorno y crear nuevas variables de entorno, para conocer mas informacion al respecto referirse a la [documentacion oficial](https://www.npmjs.com/package/dotenv)

## Como instalar

Basta con ejecutar el codigo

```bash
npm install dotenv --save
```

## Como usar

Podemos importarlo usando require

```javascript
require('dotenv').config()
```

En ES6 tambien podemos utilizar el import

```javascript
import * as dotenv from 'dotenv'
```

dotenv tiene una configuracion inicial que es muy util y usualmente no requiere de mayores modificaciones, para invocarla debemos usar

```javascript
dotenv.config();
```

Esta libreria automaticamente convertira cualquier componente del archivo .env en una variable de entorno, para acceder a cualquier variable de entorno basta con llamar

```javascript
process.env.NOMBRE_VARIABLE
```

