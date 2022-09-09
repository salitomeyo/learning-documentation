---
id: pci4rtrqkt6341a5sd8eez3
title: SOLID-CleanCode
desc: ''
updated: 1662728801232
created: 1660332918216
---

---
This page will contain al the concepts learnt while watching the [**Principios SOLID y Clean Code**](https://www.udemy.com/course/solid-clean/) *Udemy course*


### Deuda tecnica

Significa falta de calidad em el codigo, lo que repercutira en costos futuros y requerira invertir tiempo extra en:

- Mantenimiento
- Refactorizar codigo
- Comprender codigo
- Transferencia de codigo

### Esquema de la deuda tecnica de Martin Fowler

- **Imprudente**: Es provocada a proposito por falta de tiempo o de interes
- **Inadvertido**: Es provocada por desconocimiento
- **Prudente**: Es realizada a proposito con el fin de cumplirla luego, si no se paga a tiempo puede ocasionar problemas
- **Prudente e inadvertida**: Solo se ve la deuda luego de trabajar un tiempo en un proyecto o conforme un desarrollador aprende nuevas tecnicas

>Caer en deuda tecnica es `normal y usual`, pero la diferencia entre desarrolladores experimentados es que son concientes de ella y del momento adecuado para pagarla

**Como se paga la deuda tecnica?**

##### Refactorizacion

Proceso que tiene como objetivo `mejorar el codigo` sin alterar su comportamiento, para mejorar su entendimiento y tolerancia a cambios

Es imprescindible contar con pruebas automaticas antes de refactorizar

>La mala calidad del software siempre la paga alguien, ya sea el cliente, el proovedor o el desarrollador

## Clean Code

Es aquel que se ha escrito con la intencion de que otra persona lo entienda

Para escribir **Clean Code** se deben seguir ciertas practicas:

#### Nombres de variables

- Nombres pronunciables y expresivos
- Ausencia de informacion tecnica en los nombres

>En lugar de usar *UserImplementation*, o *UserInterface* usar **User**

- Nombres segun tipo de dato

>`Arrays` Pluralizar nombres

>`Booleans` Usar variables con verbos en lugar de *open* usar **isOpen**

>`Numbers` Usar min, max, total, o totalOf

#### Nombres de funciones

- Nombres de las funciones deben representar las acciones que realizan

>Nombre comunes incluyen **get**, **find**

>Si realizan acciones recibiendo parametros especificos es comun incluir **by**

Cada funcion realiza exactamente lo que indica su nombre

#### Nota

* Para recordar sobre funciones: 
    * Se le llama parametros de la funcion a los atributos que recibe una funcion *(en la definicion de la misma)*

    ```javascript
    function findBook(bookName: string)
    ```

    * Se le llama argumentos de la funcion a los atributos que enviamos *(durante un llamado de la misma)*

    ```javascript
    findBook('El principito')
    ```

* Se recomienda limitar los parametros a 3, y ordenarlos de forma alfabetica

>Si una funcion recibe mas de 3 parametros se recomienda reemplazar por `interface`

* La simplicidad es fundamental, deben seguir el  **Principio de responsabilidad unica**, cumplir una tarea y hacerla bien
* Deben tener un tamaño reducido (se recomiendan menos de 20 lineas)
* Evitar el uso del else
* Priorizar el uso de la condicional ternaria

>Ejemplo de condicional terciaria: 

```javascript
return ( isRetired ) ? 3000 : 4000;
```

#### Nombres de Clases

- Nombres de clases deben ser sustantivos o frases de sustantivos *(Pero no deben ser muy genericos ni muy espeificos)*

### Principio DRY

**Dont Repeat Yourself**

* Evita duplicidad
* Simplifica pruebas
* Ayuda a centralizar procesos

### Clean Code - Clases

Deben seguir el **Principio de responsabilidad unica**

Hay que tratar de evitar el uso de los extends (herencia), ya que el extends rompe el principio de resopnsabilidad unica

Se debe **priorizar el uso de la composicion** sobre el uso de la herencia

Se deben conservar las recomendaciones del lenguaje usado pero en general se puede conservar el siguiente orden:

* Comenzar con las propiedades
    * Propiedades estaticas
    * Propiedades publicas

* Metodos
    * Constructores estaticos
    * Constructor
    * Metodos estaticos
    * Otros metodos (de mayor a menor importancia)
    * Getters y Setters


### Clean Code - Comentarios

**Los comentarios deberian ser la excepcion no la regla**

Nuestro codigo deberia ser suficientemente auto explicativo

>En caso de necesitar comentarios estos deberian explicar el **Porque** en lugar del *Que* y el *Como*

### Clean Code - Uniformidad

**Problemas similares deberian tener soluciones similares**

En estructura del codigo, en los nombres de variables y directorios, respetar la identacion

## STUPID

Son 6 code Smells que debemos evitar

* **S**ingleton
* **T**ight Coupling
* **U**ntestability
* **P**remature Optimization
* **I**ndescriptive Naming
* **D**uplication

>Un code smell hace referencia a una mala practica en el codigo que debemos evitar

#### Singleton

* Es dificil de testear
* Viven en un contexto global
* Son modificables por cualquiera en cualquier momento por lo que son poco rastreables

#### Tight Coupling

* Los componentes son dependiente e insuficientes por si solos, hay muchas referencias de un componente a otro

>**Se busca bajo acoplamiento y alta cohesion**

* La cohesion se refiere a lo que la clase puede hacer

* El acoplamiento se refiere a cuan relacionadas o dependientes son dos clases entre si

#### Optimizaciones prematuras

No debemos anticiparnos a los requisitos y desarrollar abstracciones involuntarias añadiendo complejidad accidental

#### Duplicidad

Existen 2 clases

* Real: Hace refencia a codigo identico que cumple la misma funcion, un cambio implica actualizar codigo identico en varios lugares, incrementa posibilidades de typos

* Accidental: El codigo luce similar pero cumple tareas distintas, se puede trabajar con parametros u optimizaciones

#### Otros "code smells"

[Refactoring, smart programming](https://refactoring.guru)

* **Inflacion**: Los metodos crecen continuamente, se debe buscar separar en varios metodos si un metodo se vuelve muy extenso (esto mismo puede suceder en clases)

* **Obsesion primitiva**: Evitar incorporar variables primitivas, a largo plazo es mejor actualizar metodos y clases

#### Code smells - Acopladores

* **Feature envy**: Una funcion, clase o metodo accede con mayor frecuencia a los valores y metodos externos

* **Intimidad inapropiada**: Una clase usa campos y metodos internos de otra clase, las clases deben saber lo menos posible de las demas clases

* **Cadena de mensajes**: Una funcion realiza llamados a otras funciones para realizar una tarea

* **Middle man**: Una clase que solo se utiliza para delegar funciones a otra, estas clases no deberian de existir







