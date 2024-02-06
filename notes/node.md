---
id: tdbvz4srld6cfptu6vomxl9
title: Node
desc: ''
updated: 1662728988237
created: 1661527872594
---

This page will contain al the concepts learnt while watching the [**Node: De cero a experto**](https://perficient.udemy.com/course/node-de-cero-a-experto/) *Udemy course*

## Instalar node

En primera instancia es necesario [instalar node](https://nodejs.org/es/) basta con instalar la version LTS ya que es mas estable

## Que es node

Es un lenguaje de backend que corre sobre el motor V8 de google, cambia el lenguaje de node a lenguaje de maquina

Es un built-on de javascript por lo que la sintaxis es muy similar, esto tambien significa que **podemos correr cualquier archivo de js usando node** sin necesidad de usar un navegador web

## Que puedo hacer con node

* Usar sockets para comunicacion cliente-servidor
* Manejo de archivos en FileSystem y cargas simultaneas
* Servidores locales y remotos en tiempo real
* Conexiones a base de datos
* Creacion de servicios REST con express

## Non blocking I/O

Node es muy popular ya que sus entradas y salidas son no bloqueantes, es decir es asincrono, las entradas y salidas **se ejecutaran en el background sin bloquear la ejecucion** del resto del codigo

## Ciclo de vida

Los programas ejecutados con node siguen un orden de ejecucion que se divide en 3 pilas

<details>
<summary><strong>Pila de procesos (call back)</strong>
</summary>
Registra todas las funciones en lectura, la primera funcion en la pila de procesos siempre sera el main()
<br>
Todas las funciones que no tienen tiempo de espera son ejecutadas en orden de entrada (que por defecto en apps sincronas es el orden de lectura), es decir cada una de las funciones se elimina de la pila conforme se ejecuta
</details>
<details>
<summary><strong>Node APIs</strong>
</summary>
Guarda un registro a todas las peticiones que estan en proceso pero que todavia no tienen una respuesta, es decir cualquier peticion que tenga un timeout o un tiempo de respuesta estara almacenada en la pila de Node APIs (independientemente de si el proceso tiene un tiempo de respuesta de 0 seg se enviara a esta pila)
<br>
Los procesos que entran a esta pila entran en orden de escritura pero salen en orden de finalizacion, es decir, son asincronos, cada proceso que se haya completado saldra inmediatamente de la pila sin tener en cuenta el orden
</details>
<details>
<summary><strong>Cola de callbacks</strong>
</summary>
Esta pila guarda un registro de todas las peticiones que ya han sido completadas (todas las peticiones que salen de la pila de Node APIs)
<br>
Esta almacena los registros en orden de llegada y los va enviando a la pila de procesos en la ultima posicion, es decir un proceso asincrono sin importar cuanto tiempo tarde se va ejecutar luego de todos los procesos sincronos 
</details>

### Nodemon

[nodemon](https://www.npmjs.com/package/nodemon) es un package de node que nos ayuda a desarrollar aplicaciones de node. 

Con el podemos crear un servidor que permite `ver los cambios a los archivos en tiempo real`, en lugar de tener que correr los archivos cada vez

Para levantar el servidor basta con ejecutar

```bash
nodemon nombreArchivo
```

## Como leer los argumentos en consola

Al ejecutar un comando en consola usando node este se guarda en una variable process, y accediendo a su atributo .argv podemos ver todos los argumentos

```bash
process.argv
```

Con ayuda de este atributo podemos ejecutar cualquier funcion dependiendo de los atributos enviados en el comando de ejecucion. Esta es una forma de **leer los argumentos en consola** pero es muy **complejo manejar todas las validaciones** necesarias para ejecutar el codigo, por esto usaremos un package que ya tiene todas estas validaciones llamado `Yargs`



