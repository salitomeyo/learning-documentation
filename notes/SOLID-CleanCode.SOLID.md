---
id: b7qtl55iefqv4k3r287o71o
title: SOLID
desc: ''
updated: 1660341226362
created: 1660333010451
---

## SOLID Principles

Los principios solid nos indican como organizar funciones y estructuras de datos en componentes, y como dichos componentes deben estar interconectados

* **`S`**ingle Responsibility Principle (SRP)

* **`O`**pen/Closed Principle (OCP)

* **`L`**iskov Substitution Principle (LSP)

* **`I`**nterface Segregation Principle (ISP)

* **`D`**ependency Inversion Principle (DIP)

### SRP

Una clase deberia tener una unica responsabilidad, componentes que solo esten expuestos a un agente de cambio

>Podemos detectar violaciones si encontramos *nombres genericos*, *cambios afectan clases*, *clase involucra multiples capas*, *muchos metodos publicos o impotaciones*, *muchas lineas de codigo*

### OCP

Establece que las entidades (clases, modulos, metodos) deben estar abiertas para la extension pero cerradas para la modificacion

Que una clase o metodo reciba diferentes parametros no deberia implicar cambios de codigo ya que el codigo deberia permitir la extension

Se recomienda usar el `Patron adaptador`

>Podemos detectar violaciones si *Hay que realizar cambios constantemente*, *una clase o modulo afecta muchas capas*

### LSP

Siendo U un subtipo de T, cualquier instancia de T deberia poder ser sustituida por cualquier instancia de U sin alterar las propiedades del sistema

>Se deberia siempre intentar utilizar metodos que puedan recibir la clase padre, en lugar de metodos que hagan diferenciacion entre las subclases ya que esto rompe no solo LSP sino a su vez OPC

### ISP

Los clientes no deberian estar obligados a depender de interfaces que no utilizan

>Si interfaces violan los principios de SPR y LSP probablemente tambien violen el ISP

### DIP

* Los modulos de alto nivel no deben depender de modulos de bajo nivel. 
* Ambos deben depender de abstracciones. 
* Las abstacciones no deben depender de concreciones. 
* Los detalles deben depender de abstracciones.

Los **componentes de alto** nivel son los que pertenecen a la capa de negocio

los **componentes bajo nivel** son los que estan proximos a la infraestructura, UI, persistencia, comunicacion con APIs externas

Queremos poder ver las dependencias de forma sencilla, sin dependencias ocultas


