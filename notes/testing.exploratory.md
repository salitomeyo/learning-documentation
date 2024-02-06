---
id: p29mklg5qfamb404vrf7vc0
title: Exploratory
desc: ''
updated: 1661887957097
created: 1661872342496
---

This page will contain al the concepts learnt while watching the [**Testing exploratorio para agilizar tus pruebas**](https://perficient.udemy.com/course/testing-exploratorio-para-agilizar-tus-pruebas) *Udemy course*

## Exploratory testing

Es mas utilizado en metodologias agiles, normalmente no contiene una documentacion tan extensa como los demas tipos de testing

Es la actividad intelectual del testing, se busca descubrir e investigar, diseñar e implementar pruebas, se busca hacer todo en simultaneo

### Clasificacion

* Ad hoc
* Scripted testing
* Exploratory testing

#### Ad hoc

Es un testing sin plan objetivos, sin un metodo, es una mala practica

#### Scripted testing

Es rigido, esta escrito de antemano, se debe seguir el plan, por esto mismo son automatizables

* Se parte de los requerimientos
* Casos de prueba por adelantado
* Confirmacion de los requerimientos
* En fasis en predecir errores y decidir previamente
* Analogia con un discurso
* El control lo tiene el script

#### Exploratory

Debe hacerse de `forma manual, ya que no hay un plan`, adicionalmente no es automatizable, es usualmente usado por tester senior ya que es necesario y fundamental tener experiencia, ser metodico

* Se parte de la aplicacion
* Casos de prueba durante la ejecucion
* Investigacion de la aplicacion
* Enfasis en la adaptacion y el aprendizaje
* Analogia con una conversacion
* El control lo tiene la mente del tester
* Uso libre de la aplicacion

>Cem Kaner "Es un estilo de testear software que enfatiza, la libertad personal y responsabilidad individual del tester, para optimizar de manera continua el valor de su trabajo tratando al aprendizaje, diseño y ejecucion de pruebas, como actividades que se apoyan mutuamente y corren en paralelo a lo largo de un proyecto"

### Objetivos

* Entender la aplicacion, interfaces funcionalidades
* Exhibir su comportamiento
* Encontrar defectos

### Ventajas y desventajas

#### Ventajas

* Util en contextos con poca documentacion
* Mas y mejores escenarios
* Desafia la creatividad e intuicion
* Bajo costo
* Mantenible

#### Desventajas

* Depende de los skilss, experiencias y conocimientos del tester
* Requiere cierto seniority
* Dificultad para obtener algunas metricas

### Cuando usarlo

* Cuando la documentacion es nula o escasa
* Cuando hay poco tiempo para su implementacion
* En contextos agiles ya que presenta mejor adaptabilidad a los continuos cambios 

Se puede usar de forma no excluyente con el scripted testing


## Session-Based testing

* **Session**: Es un periodo de tiempo acotado dedicado a cumplir con un objetivo especifico de las pruebas, se recomienda que su duracion sea entre 45min y 2h

>Is not a test case or bug report, is the basic testing work unit. What we call a session is an uninterrupted block of reviewable, chartered test effort

* **Charter**: Son las metas para una sesion, una plantilla propuesta incluye

*Explore* 
<br>
*With*
<br>
*To discover*

* **Session sheet**

* **Debrief**: Se deben discutir los PROOF

    * **P**ast: what happend during the session
    * **R**esults: what we achieve during the session
    * **O**bstacles: which problems did we find during the session
    * **O**utlook: What we need to do, whats next
    * **F**eel: The tester perseption during the session

### Como hacer pruebas exploratorias

Primero debemos **planificar** la o las sesiones que vamos a tener, identificar los riesgos durante el sprint y hacer una session por cada riesgo

Luego debemos realizar la **ejecucion**, anotar los caminos recorridos, las preguntas que surgen, los problemas encontrados

Finalmente **informar**, hay que informar lo encontrado durante la session, la documentacion debe ser accesible y legible

## Estrategias de testing exploratorio

* In the small
* In the large

### Small

Decisiones tomadas durante la ejecucion de las pruebas, son decisiones particulares, repetitivas, constantes y multiples

Basado en
* Que el testing exhaustivo no es posible
* Las tecnicas para diseñar casos de prueba

**Clasificacion de las pequeñas decisiones**

* Entradas 
* Estados
* Caminos
* Datos del usuario
* Ambientes

#### Entradas (Inputs)

Donde se puede estimular al sistema para generar una interaccion, hay infinitas posibilidades, es crucial tener en cuenta como seleccionamos las variaciones en las entradas. Se deben considerar

* Inputs particulares
* Inputs combinados 
* Orden
* Positivos y negativos
* Legal o ilegal
* Normal o especial
* Provistor por el usuario o por defecto

Algunas formas de prevenir estos errores son:

* Bloqueos
* Validaciones sobre datos de entrada
* Excepciones (aveces son poco especificas)

#### Estados (states)

No son estaticos sino que deben tenerse en cuenta la consideracion de acciones previas

#### Caminos (code path)

Son las sentencias que se ejecutan de linea a linea, por ejemplo

* Decisiones (if/then/else)
* Opciones (Case)
* Iteraciones (For/while/repeat)

#### Datos del usuario (User data)

* BDD
* Control de los datos
* Simil produccion: generacion vs replica
* Performance

#### Ambientes de ejecucion (Enviroment)

* Portabilidad
* El ambiente interactua permanentemente con el software

### Large

Decisiones tomadas durante la planificacion, son decisiones generales, como se van a organizar los testers

Estan basados en la metafora del turismo, para decidir que caminos recorrer en las exploraciones. Como es tan extenso se propone dividirlo  en diferentes distritos, los distritos propuestos:

* De negocios (Funcionalidades mas importantes del negocio, el core)
* Historico (el codigo legacy)
* Turistico (lugares donde se concentran los usuarios nuevos, e.g. login)
* Entretenimiento (funcionalidades de soporte)
* Hotelero (procesos que corren cuando hay pocos usuarios)
* Sordido (vulnerabilidades, forzar la aplicacion a proposito)

Los distritos y los tours que componen cada uno de los distritos no son obligatorios, es solo una forma de verlo

Se recomienda usarlos ya que evita el error comun de dividir por funcionalidad, nos permite ponernos de acuerdo y homogeneizar un poco la exploracion, permite su combinacion estrategica, entra en el **Scenario based exploratory testing**, permite la creacion de tours propios

### Operadores

* Permiten introducir variaciones o variaciones a los sistemas que estamos recorriendo. Al introducir variaciones se generan escenario derivados, se puede aplicar uno o varios. Cuantos y cuales es una decision estrategica, los operadores mas comunes son

* Insertar
* Eliminar
* Reemplazar (diferentes caminos para conseguir el mismo resultado)
* Repetir (intercalar pasos repetitivos)
* Sustituir (Cambiar variables)

