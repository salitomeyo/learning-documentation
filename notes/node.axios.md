---
id: vxqppu9ylf6sb0cwr9mv3zc
title: Axios
desc: ''
updated: 1662728965796
created: 1662671387384
---

Es un package de npm que nos permite trabajar con peticiones http, es basado en promesas, para ver mas informacion acerca de su utilizacion referirse a [la documentacion oficial](https://www.npmjs.com/package/axios)

## Instalacion

Basta con ejecutar el siguiente codigo en la consola de comandos

```bash
npm i axios
```

## Como usar

En la documentacion oficial de axios indica que se debe utilizar con `type:'commonjs'`, si nuestro proyecto de package.json tiene esta propiedad asi podemos usar 

```javascript
const axios = require('axios').default;
```

Pero usualmente me encuentro con la problematica de estar utilizando `type:'module'` lo cual impide esta implementacion ya que se depreca el uso del require, y he encontrado poca documentacion al respecto pero basta con utilizar

```javascript
import axios from 'axios';
```

Una vez lo tenemos importado basta con llamar a cualquiera de sus metodos lo cual resulta bastante intuitivo 

```javascript
axios.get('https://www.dominio.com')
```


