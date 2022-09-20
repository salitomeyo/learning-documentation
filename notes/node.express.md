---
id: 2p3csbmmw0gbf0n5eo181d4
title: Express
desc: ''
updated: 1662758583736
created: 1662742529951
---

Express its a package that help us built and manage webservers, To get more detailed information about it refer to the [official documentation](https://expressjs.com/es/starter/installing.html)

## Installation

Because it is a npm package we can simply use

```bash
npm i express --save
```

## How to use

After we install the package using npm we need to import it, to do this we use `require()`

```js
const express = require('express');
const app = express();
```

To create a hello world server we simple need to define our first request and any port to listen

```js
app.get('/', (req, res) => {
  res.send('This is the home reques')
})

app.listen(8080)
```

### Different request paths

Having the initial request we can also specify any other request, to differentiate request we use different routes for example

```js
app.get('/hello-world', (req, res) => {
    res.send('this is the Hello World')
})
```

### Default return

An we can also specify a default response, this will be called for any other request that does not match the defined request

```js
app.get('*', (req, res) => {
    res.send('404 | Page not found')
})
```

### Types of return

We can return a string but this type of return is often overlooked because it lacks functionality

```js
app.get('/', (req, res) => {
    res.send('Something')
})
```

If instead of returning a string we want to return a json we can use 

```js
app.get('/', (req, res) => {
    res.json({ name: 'Salome' })
})
```

We can also return files, we do this for example when we are builing a website, the first step to do this is to configure the path to the folder where we can find the files to return, this folder should be called public and be place on the root of the project

```js
app.use( express.static('public') );

app.get('/', (req, res) => {
    res.sendFile(__dirname + '/public/elements.html')
})
```

### Types of request

Also we can execute any and all the posible http request in express just calling the function name for example

```js
app.post('/elements', (req, res) => {
    res.json({ name: 'Salome' })
})

app.put('/elements', (req, res) => {
    res.json({ name: 'Salome' })
})

app.delete('/elements', (req, res) => {
    res.json({ name: 'Salome' })
})
```

### Middleware

Functions that add extra functionalities to our webserver, they are executed when the server is first started, one common middleware is the reference to the public folder

### Server using class

La ventaja de montar un servidor de express usando clases es que esta clase se puede reutilizar en cualquier otro proyecto facilmente, a continuacion se muestra un ejemplo reutilizable

```js
const express = require('express');

class Server {
    constructor() {
        this.app = express();
        this.port = process.env.PORT;

        this.middlewares();

        this.routes();
    }

    middlewares() {
        this.app.use( express.static('public') );
    }

    routes() {
        this.app.get('/api', (req, res) => {
            res.json({
                msg: 'get API'
            });
        })
    }

    listen() {
        this.app.listen( this.port, () => {
            console.log('Server running on port', this.port);
        })
    }
}

module.exports = {
    Server
}

```

Este modelo se puede convertir en un modelo muy pesado y de facil manejo conforme crecen las rutas, el modelo mas comun incluye separar las rutas de este archivo

### Routes

Para separar las rutas usualmente se crea una carpeta routes y en ella se hacen archivos por cada uno de los servicios, el siguiente es un ejemplo de la estructura que deberian seguir cada uno de los archivos de routes

```js

const { Router } = require('express');

const router = Router();

router.get('/api', (req, res) => {
    res.json({
        msg: 'get API'
    });
})

module.exports = router;
```

Una vez tenemos definidas todos los request de un archivo lo importamos a nuestra clase utilizando

```js
routes() {
    this.app.use( this.userPath , require('../routes/user'));
}
```
