---
id: ggksgdfqj3hig9jbetpiexs
title: Uuid
desc: ''
updated: 1662728998322
created: 1661889617381
---

UUID es un package de npm que nos permite **crear ids unicos randomizados** facilmente, los id generados son seguros criptograficamente y completamente unicos

## Como instalar

Como es un package de npm se puede consultar toda la informacion sobre el mismo en [UUID](https://www.npmjs.com/package/uuid) pero basta con usar el comando

```bash
npm i uuid
```

## Como usar

Las ultimas versiones de uuid ya no permiten la importancion usando require, por lo que es necesario hacer unas modificaciones antes de poder utilizarlo en un proyecto

1. En el `package.json` es necesario agregar 

```javascript
"type": "module",
```

2. Si el proyecto estaba usando importanciones tipo require es necesario reemplazarlas todas por `import` y adicionalmente agregar la importacion de inquirer

```javascript
import { v4 as uuidv4 } from 'uuid';
```

3. Finalmente es necesario modificar todos los exports que siguieran el patron `module.export`, por

```javascript
export{}
```