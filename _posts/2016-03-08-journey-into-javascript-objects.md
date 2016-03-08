---
layout: post
section-type: post
title: Javascript Objects
categories: ['programming']
tags: [ 'javascript']
---


# Journey Into Javascript

## Objects
Objects store information (properties) about a given entity.  
 * use DOT NOTATION only for STRINGS  
 * use BRACKET NOTATION with VARIABLES and NUMBERS  
 * You can only use dot notation if your property is an alphanumeric string that starts with a letter

```javascript
// Object literal  
var student = { name: 'Paul Jones'};  
// Dot notation
student.location = 'Sydney, AU';
// Bracket notation
student['twitter'] = '@shmiko';
```    
In JS memory the object is represented like this:

```javascript
{  
  "name": "Paul Jones",
  "location": "Sydney, AU",
  "twitter": "@shmiko"
}  
```  

```javascript
// Object literal  
var student = { name: 'Paul Jones'};  
// Dot notation
student.location = 'Sydney, AU';
// Bracket notation
student['twitter'] = '@shmiko';
``` 

Transform from dot notation to bracket notation.  
```javascript
// with dot notation
student.name = "Paul"; //"Paul"  
// with bracket notation  
student['name'] = "Paul"; //"Paul"  
```

Value in memory is the same.  

DOT === SHORTHAND  
Think of dot notation as  being shorthand for bracket notation that can only be used when the property name is a string that starts with a letter... it's easier and faster to type.  
You can imagine that under the hood, the JavaScript engine will take the string that's after the dot and insert it between some brackets.

Using numbers  
```javascript
var Hunter = {};          
Hunter.007 = "James Bond"; // Uncaught SyntaxError: Unexpected number  
Hunter['007'] = "James Bond"; //{"007" : "James Bond"}  
```

More string examples  
```javascript
var kid = {};            
kid["name"] = "Robinson";  
var key = "name";  
kid['key']; //undefined  
kid.key; //undefined              
kid[key]; //"Robinson"  
```

Using special characters  
```javascript
var child = {};              
child["name"] = "Bob";  
child["^&*"] = "testing 123";  
var test = child["^&*"];  
child.@#! //SYNTAX ERROR  
```
result is
```javascript
student =
{  
  "name" : "Bob",  
  "^&*" : "testing 123"  
}   
```   

Summary of DOTS VS Brackets  

**Dots**   
strings :+1:      
numbers :x:  
quotations :x:    
special chars :x:  
expressions :x:  

**Brackets**  
strings - in "" :+1:  
special chars - in "" :+1:    
other primitives :+1:    
variables :+1:  
expressions :+1:  

---
## Arrays  
Arrays store collections of values.  
```javascript
 // Array literal  
 var students = [ 'Paul' ];    
 // Bracket notation for access/assignment  
 students[0]; //'Paul'  
 students[1] = 'Richard';  
 // Dot notation for native properties  
 students.length; //2  
```  
 In JS memory the array is represented like this:
```javascript
 {  
   "0": "Paul",  
   "1": "Richard",  
   "length": "2"  
 }  
```

 Arrays are special objects.  
  * numeric indexes  
  * native length property  
  * native methods ie (push,pop)  

---

## Functions  
 Functions are also objects, known as first class objects  
```javascript
 var treasureChest = function(){  
   return "you get nuthin' doing that!";  
 };  

 treasureChest.treasureMap = 'three steps forward';  
 console.log(treasureChest.treasureMap);  
 //'three steps forward'  
```

 So what can we do with objects, arrays and function?  
 Well since they are all objects we can do the same thing to each of them.  
 Examples are:  
  * Add a property to them like this:  
```javascript
  var mysticalAnimal1 = {};  
  mysticalAnimal1.type = 'dragon';  
  console.log(mysticalAnimal1);  
  //'Result is { type: 'dragon' }'  
```  
  * Assign a variable to point to them like this:  
```javascript
  var animalMystical = mysticalAnimal1;  
  console.log(animalMystical);  
  //'Result is { type: 'dragon' }'  
```
  * Overwrite a variable like this:  
```javascript
  animalMystical.type = 'spider';  
  console.log(animalMystical);  
  //'Result is { type: 'spider' }'  
```
  * Pass it in as an argument to a function like this:  
```javascript
  var testType2 =  function(str){  
  	var correctAnswer = str;  
  	console.log('testType2 correctAnswer is ',correctAnswer);  
  };  
  testType2(animalMystical);  
  //'Result is testType2 correctAnswer is  { type: 'spider' }'  
```
  * Return it as a value from a function like this:  
```javascript
  var testType3 =  function(str){  
    console.log("testType3 ",str);  
    return str;  
  };  
  testType3(animalMystical);  
  //'Result is testType3  { type: 'spider' }'  
```         
