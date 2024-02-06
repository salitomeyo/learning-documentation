---
id: i6qqlk50p7t4j3i2kujw0rm
title: HTTP
desc: ''
updated: 1662741204823
created: 1662738957164
---

Its an tool integrated by default with node, we can use it to build servers

## How to use

Because it is integrated by default we dont need any additional instalation, any js file running in node can access this functionality

```js
const http = require('http');
```

To build a server we just have to use `.createServer()` this functionality will use two params req and res, req being the request made and res the response of that request 

```js
http.createServer((req, res) => {
    res.write('Hola mundo');
    res.end();
}).listen( 8080 );
```

In the `listen()` we have to specify any port we will like to keep track of, in this case if we go to `http://localhost:8080/` we will be able to see the response

We have lots of functionalities to work with http request, but here i will refer to the more useful

### Change res status code

for example we can change the status code response

```js
res.writeHead(201);
```

### Change res content-type

```js
res.writeHead(200, {'Content-Type': 'application/json'});
```

### Change res to file download

```js
    res.setHeader('Content-Disposition', 'attachment; filename=lista.csv');
    res.writeHead(200, {'Content-Type': 'application/csv'});
```

Cabe destacar que aunque http tiene muchas funcionalidades y nos permite controlar peticiones http puede resultar tedioso a la hora de crear muchas peticiones, por esto usualmente se recomienda el uso de otras herramientas que facilitan estos controles como express

