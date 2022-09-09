---
id: tn8jm1lq6a5u1ffm0kry2vf
title: Classes
desc: ''
updated: 1662727702958
created: 1660836951231
---

## Classes

Son muy utilizadas en el paradigma de la **programacion orientada a objetos**, ya que permiten definir plantillas para objetos, a asignarles propiedades y metodos que todas las instancias de la clase deben tener

Son definidas usando la palabra reservada **class** usualmente se usa *`Upper Camel Case`* para nombrarlas, deben contener un constructor y para crear instancias se usa **new**

Para referirse a las propiedades y metodos dentro de la clase se usa el **this**

```javascript

class NombreClase {
    propiedad1 = '';
    propiedad2 = '';

    constructor(propiedad1 = 'Valor por defecto') {
        this.propiedad1 = propiedad1;
    }

    set setPropiedad2( propiedad2 ) {
        this.propiedad2 = propiedad2;
    }

    get getPropiedad2() {
        return this.propiedad2;
    }

    metodo() {}
}
```

### Set and Get

Usualmente se definen luego del constructor, `sirven para dar acceso` (a funciones externas) de modificar y acceder al valor de las propiedades de la clase

### Propiedades y metodos estaticos

Sirven para definir propiedades y metodos que **pueden ser usados sin necesidad de crear una instancia de la clase**

### Herencia

Sirve para extender una clase padre con metodos y propiedades comunes que serviran para crear varias clases hijos

```javascript
class Person {

    static _count = 0;
    name = '';

    constructor(name = 'No name') {
        this.name = name;
        Person._count++;
    }

    metodo() {
        console.log('Something');
    }
}

class Student extends Person {
    grade = 'sin grado';

    constructor(name, grade) {
        super( name );
        this.grade = grade;
    }

    metodo() {
        console.log('Something else');
        super.quienSoy();
    }
}

```

### Propiedades privadas

Son **propiedades protegidas, no pueden ser accedidas fuera de la clase** a menos que se utilicen los getters y setters

Actualmente la implementacion de propiedades privadas de clases de javascript esta en proceso, por lo que este metodo `no es aceptado por todos los navegadores` pero para convertir una propiedad en privada basta con usar # antes del nombre de la misma

```javascript
class ClassName {
    #property = '';
}
```

Para saber en que [navegadores actualmente esta implementada la funcionalidad de propiedades privadas](https://caniuse.com/mdn-javascript_classes_private_class_fields)

### Singleton

Son `instancias unicas de una clase`, para esto se utiliza una propiedad estatica que tiene constancia de la instancia creada y sobreescribe cualquier otro llamado para crear una instancia

```javascript
class Singleton {
    static instancia;
    name = '';

    constructor ( name = '' ) {
        if (!!Singleton.instancia) {
            return Singleton.instancia;
        }
        
        Singleton.instancia = this;
        this.name = name;
    }
}
```

#### Nota

Javascript no permite la sobrecarga del metodo constructor, pero esto se puede realizar utilizando metodos estaticos y que al invocarlos estos creen la instancia

```javascript
class Person {
    static porObjeto({ name, lastname }){
        return new Person( name, lastname );
    }

    constructor ( name, lastname ){
        this.name = name;
        this.lastname = lastname;
    }
}
```

