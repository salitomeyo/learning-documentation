---
id: mkk2ixcjc15c770zj5pirdv
title: Postman
desc: ''
updated: 1663880234853
created: 1663613274681
---

Is a tool we can use to test and understand APIs, this is the resources and information gather during the development of the [Postman: The Complete Guide - REST API Testing](https://www.udemy.com/course/postman-the-complete-guide/) Udemy course, for better information i recommend checking the course 

>You can also check the following resource [Postman Guide](https://postman-quick-reference-guide.readthedocs.io/_/downloads/en/latest/pdf/)

## Whats an API?

Is an interface to some data on a server usually stored on a database, **it allows us to communicate and exchange data with the server**, without it the server will be unnacesible to the outside world, it stands for

* **A**pplication
* **P**rogramming
* **I**nterface

Some important thing to take notice,

* They are design to be used from programs
* They dont have a friendly interface


### Interface 

Is a contract, a way to bring different parties together, it establish a set of rules and allow interoperability as long as the rules are being followed

## Why postman?

It allows us to connect and use API through a somewhat intuitive interface without needing to write any code 

With postman we can access different endpoints of any API including locally hosted ones

### Endpoint

Different addresses between an API where we can find information

## Postman client

Postman is a client that uses the http protocol to send requests and receive responses from a server

https is the secure version of http, we must use when possible because this allows for encryption which means nobody outside of the client making the request can read the information send

### Request

In general terms it contains

* Address
* Request method
* Headers
* Body

We can find all this information in the top part of postman

We can understand a request like a letter, the address and request method represent the address and receiver of the letter, the headers are the additional details like stamps and codebars all of this represent the envelope, and the body is the contents of the letter

### Response

In general terms it contains

* Status code
* Headers
* Body

We can find this information on the bottom part of postman

## Uses of postman

Postman has a lot more functionalities than just testing capabilities

* Manual API testing
* Mock Server
* Collaboration (team library)
* API documentation
* Script workflows
* Script tests
* Automatic API testing:
    * Newman
    * Collection runner
    * Monitors

## Postman Collection

Is a folder that stores multiple request, it is usually used to separate different APIs

To save any request we need to save it inside a collection

### Variables

Usually all the requests inside an API tend to star exactly the same, in order to avoid retyping the same thing over and over again we can use variables

We can save this variables globally which means they will be accesible inside any collection, or we can save them inside a collection, which means they will only be accesible inside the given collection (this is a more common use than saving them in the global scope)

Take into account that variables have initial value and current value, when we share a collection only the initial values are public, the current values are private  for everyone

### Query params

Keep in mind that query params are case sensitive, which means we need to put the key names exactly like the API documentation tell us, any kind of change in capitals may make the request invalid

## Types of requests

* **GET**: We usually use get to retrieve parameters, the get request doesn't have a body 
* **POST**: We usually use post when we are trying to create new information
* **PUT** or **PATCH**: We usually use when we are trying to update information, altought post can also be used for this purpose
* **DELETE**: We use this to delete information
* **HEAD**: Is a special type of request, we usually use it in order to find the health of a API endpoint or to figure out if the information we are sending is correct, it doesn't have a response body

# Testing in postman

## Test

A test is commonly a simple assertion, take into account that one request can have multiple tests and the test only run After the request is completed

To create tests in postman we can simple go to the tests tab in the top part of postman

The sintaxis of the postman tests is quite simple, you just have to use the key word **pm** and its methods

### Sintaxis

* The first parameter is the test name, as a string
* The second parameter is a so-call callback function which is called when the underlying execution has finished
* pm.response - is the response assertion APi and can make assertions on the response object (status code, headers, body)

```js
pm.test("Name of the test", function () {
    ...code
})
```

### Test Status code

We can simple test the status code getting the response status

```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

### Variables

In postman we can create variables in different scopes, they have to follow the DRY principle, they are usually used as placeholders and follow similar rules to any programming language

The scope of the variables go as follows 

* Global
* Collection
* Environment
* Data
* Local

#### Global variables

They are used for general purpose, ideal for quick results and prototyping

>Best practices
* Avoid usign as much as possible
* Clear / remove variables once you do not need them
* Get variables in scripts usign the scoped getter

To define global variables we use

```js
pm.globals.set("variable_name", value)
```

And to access them we can simply use their name in any other part of postman

```js
pm.globals.get("variable_name")
```

We can also delete global variables

```js
pm.globals.unset("variable_name")
```

And completely clear all global variables usign

```js
pm.globals.clear()
```

#### Enviroment variables

They are similar to global variables but with a narrower scope

>When to use
* Storing enviroment specific information
* URLs, authentication credentials
* Passing data to other requests

* Ideal for switching between different setups or when working with different servers
* Same usage in the request builder as with global variables

>Best practices
* Remove variables once you do not need them
* Avoid mixing with global variables
* Fet variables in scripts using the scoped getter

To define enviroment variables we use

```js
pm.enviroment.set("variable_name", value)
```

#### Collection variables

They are tied to a collection and cant be shared by multiple collections

>When to use
* Any variables / constants
* URLs / authentication credentials if only one enviroment exists
* Eliminate duplicate variables in environments

#### Data variables

Used whe working with multiple data-sets, exist only durign the execution of an iteration, can only be set from a CSV or a JSON file

##### Sessions

Sessions provide an additional layer when working with variables

### Pre-request scripts

Similar to test scripts but with no assertions, ideal for making your request dynamic, they are usually used in combination with variables

## Assertions

First of all its important to parse the response body, there are 5 types of parse possible

* JSON

```js
pm.response.json();
```

* XML 

```js
xml2Json(responseBody);
```

* HTML

```js
cheerio(pm.response.text());
```

* Plain-text

```js
pm.response.text();
```

* CSV

```js
csv-parse/lib/sync
```




