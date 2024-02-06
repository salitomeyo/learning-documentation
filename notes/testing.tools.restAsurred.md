---
id: y3v355ov07rsmiseisavfeu
title: restAsurred
desc: ''
updated: 1662727664901
created: 1662153300240
---


Its a Java Library for testing RESTful Web Services, used to invoke REST web services and check responses

## Why RestAssured

* You can check the status of the code, the message and even the body of the response.

* They are easy to integrate with tests of all kinds: functional, unit, integrated, etc.  

* Fully coded in Java and integrable with any separate test library/framework like jUnit, * TestNG or with Maven/Gradle.  

* It can be easily integrated with Jenkins.  

* It is possible to combine with automated UI tests and does not require external tools to run.  

## How to use

RestAssured is not integrated by default with java, which means in every project you create and want to use this you have to complete the following steps 

### 1. Add the library

Inside the pom.xml we need to refer to the rest assured dependency in order to use it

To install any dependency in java we can refer to the [mvn documentation](https://mvnrepository.com), which is like the equivalent of npm for java 

For the specific [documentation on rest-assured](https://mvnrepository.com/artifact/io.rest-assured/rest-assured), remember always use the newest update in any project where you dont have an specific version requirement

Additionaly to use rest-assured we also need to use the [testng](https://mvnrepository.com/artifact/org.testng/testng), this is the dependency that will allow java to detect tests usign the decorator @Test

```java
<dependencies>
  	<dependency>
	    <groupId>io.rest-assured</groupId>
	    <artifactId>rest-assured</artifactId>
	    <version>5.0.1</version>
	    <scope>test</scope>
	</dependency>
	<dependency>
	    <groupId>org.testng</groupId>
	    <artifactId>testng</artifactId>
	    <version>7.6.1</version>
	    <scope>test</scope>
	</dependency>
<dependencies>
```

Once both dependencies are included check if they dependencies where already imported inside the **Maven Dependencies**

### 2. Import in file

In any file where you are bound to perform tests usign restAssured you need to import the following

```java
import org.testng.annotations.Test;
import static io.restassured.RestAssured.*;
```

This two imports are **always necessary** but for different types of testing you may also need a few more imports, some of the most common are

```java
import org.json.simple.JSONObject;
import static org.hamcrest.Matchers.*;
```

* [JSON.simple](https://mvnrepository.com/artifact/com.googlecode.json-simple/json-simple) lets us manipulate json objects easily, this is one of many dependencies that allows us to manipulate json, other common dependency is [Gson](https://mvnrepository.com/artifact/com.google.code.gson/gson)
* [Hamcrest](https://mvnrepository.com/artifact/org.hamcrest/hamcrest) Allows us to make matches really useful in assertions like equalTo and many others, it is a must when usign restAssured

Some other utilities useful from restassured and many others can be used but make sure you really need to use them

```java
import io.restassured.http.ContentType;
import io.restassured.http.Cookie;
import io.restassured.http.Header;
import io.restassured.http.Headers;
import io.restassured.response.Response;
import io.restassured.specification.RequestSpecification;
```

### 3. Given - When - Then 

RestAssured is a tool based in BDD (Behaviour Driven Development), which means it follows the pattern given - when - then to write tests

To make a test we can simply follow the pattern given, when then, but if the test does not require the three of them we can simply not use it.

```java
given().
	pathParam("name", pokemonName).
when().
	get("/pokemon/{name}").
then().
	statusCode(200).
	body("name", equalTo(pokemonName));
```

## Usage example

This is a simple test of the pokemonAPI usign restAssured

```java
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

import org.testng.annotations.Test;

public class PokemonApi {
	
	@Test
	public void getPokemon() {
		baseURI = "https://pokeapi.co/api/v2";
		when().
			get("/pokemon/charmander").
		then().
			statusCode(200).
			body("name", equalTo("charmander"));
	}
	
	@Test
	public void getPokemonByName() {
		baseURI = "https://pokeapi.co/api/v2";
		String pokemonName = "piplup";
		
		given().
			pathParam("name", pokemonName).
		when().
			get("/pokemon/{name}").
		then().
			statusCode(200).
			body("name", equalTo(pokemonName));
	}
}
```




