---
layout: post
section-type: post
title: Journey Into Javascript Objects
categories: ['programming']
tags: [ 'javascript']
---


## Objects
Objects store information (properties) about a given entity.  
 * use DOT NOTATION only for STRINGS  
 * use BRACKET NOTATION with VARIABLES and NUMBERS  
 * You can only use dot notation if your property is an alphanumeric string that starts with a letter  

### Declare an object is like this:  

```javascript
// Object literal  
var student = { name: 'Paul Jones'};  
// Dot notation
student.location = 'Sydney, AU';
// Bracket notation
student['twitter'] = '@shmiko';
```    

##### In JS memory the object is represented like this:  

```javascript
{  
  "name": "Paul Jones",
  "location": "Sydney, AU",
  "twitter": "@shmiko"
}  
```  



### Transform from dot notation to bracket notation.  

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

##### In JS memory the object is represented like this:  

```javascript
student =
{  
  "name" : "Bob",  
  "^&*" : "testing 123"  
}   
```   
---

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


DRY!! (don't repeat yourself)
encapsulate repeated code into a function
less typing, fewer places for bugs
Readability
use expressive names for functions
code is more organized

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
 // Last occupied index  
 var lastIndex = students.length-1;
 //pop   
 students.length; //2  
 students.pop(); //'Richard'  
 students.length; //1
 //push
 students.length; //1
 students.push('Wendy');
 students.length; //2   
```  

Array types of values.  

```javascript
 var stuff = ['fossil', 12, true];  
 var moreStuff = [undefined, null];  
 var coordinates = [ [1,10], [10,1], [11,100], [1,1] ];  
 var students = [{name:"Paul"},{name:"Richard"}]  
```  

Array Native Methods.  
.sort()  
.length()  

```javascript
 var set = [ 21, 9, 4, 2, 10];  
 // what native method can we use to help us out?  
 var sortedSet = set.sort();  
 // what native property can we use to find the maximum?  
 var max = sortedSet[sortedSet.length-1];
 // sortedSet: [2,4,9,10,21]
 // max: 21
```  

Array Summary    
* Arrays are used for storing collections of values.  
 * keys are numeric indices, making them useful for storing ordered lists of values.
 * push: arr.push(value); All .push() does is add a value to the end of an array. treasureChest.push('friends'); will add the string 'friends' to the end of our treasureChest array.  
 * pop: arry.pop(value); The .pop() method will take the last value out of an array and give it to you.  
 * unshift: The .unshift() method works just like push, but for the start of our array.    
 * shift: The .shift() method works just like pop, but for the start of our array.  
 * Array property access and assignment works the same as for objects
since keys are numbers use bracket notation.  


##### In JS memory the object is represented like this:  

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
 Functions are also objects, known as first class objects.  

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

Functions Summary  
 * DRY!! (don't repeat yourself)    
  * encapsulate repeated code into a function    
  * less typing, fewer places for bugs    

 * Control flow
  * function can be invoked wherever you want and however many times you want  

 * Readability
  * use expressive names for functions
  * code is more organized

ANONYMOUS FUNCTION  
 * An anonymous function has no name after the 'function' keyword  
 * Often used as arguments to higher order functions  

```javascript
function(item) {
 return item * 3;
}
```  
NAMED VS ANONYMOUS  

```javascript
//Anonymous function saved into a variable  
var nameImprover = function (name, adj) {  
 return 'Col ' + name + ' Mc' + adj + ' pants';  
};  
//named function  
function nameImprover(name, adj) {  
 return 'Col ' + name + ' Mc' + adj + ' pants';  
}  
//both work!  
```

INVOCATION/CALL-TIME
* Declaring a function is like creating a recipe: you decide what the steps are, but nothing actually gets made.  
* Invoking a function is like baking that recipe: now that you know what the steps are, you get to actually do them!  
* The cool part about this is that you can pass in different ingredients to that recipe each time! And each one is run totally independently of all other times that recipe has been created.  

```javascript
 //Definition/Declaration:  
 var breadMaker = function(ingredient) {  
  return 'fresh baked ' + ingredient + 'bread';  
 }  
 //Invocation:  
 breadMaker('banana nut');  
 breadMaker('guacamole');  
 //Putting () next to a function name means  
 //that you are invoking it right then.  
```

ARGUMENTS/PARAMETERS  

```javascript
 //When we define a function, what that function  
 //  takes in (it's signature) are called parameters  
 var nameImprover = function (name, adj) {  
  return 'Col ' + name + ' Mc' + adj + ' pants';  
 };  
 //When we invoke a function, what we pass in to   
 //that particular invocation are called arguments  
 nameImprover('preston','purple');  
```  

Functions Summary  
* Why are functions useful?  
 * code reuse - DRY!!
 * allow us to control when code gets executed  
 * more organized and readable  
* Definition vs Invocation  
 * defining the function is just like writing out the steps  
 * the code doesn't get run until the function gets invoked/called  
* Parameters vs Arguments (function input)  
 * parameters are variable names specified in the definition  
 * arguments are values specified at invocation    

RETURN/SIDE EFFECTS  
```javascript
//Returned value:  
var nameImprover = function (name, adj) {  
  return 'Col ' + name + ' Mc' + adj + ' pants';  
};  
//Side Effects:  
var instructorName = 'preston';  
var sideEffectImprover = function(adj) {  
  instructorName = 'Col ' + instructorName +   
    ' Mc' + adj + ' pants';  
};  
```  

More  

```javascript
//Returned value:  
var nameImprover = function (name, adj) {  
  return 'Col ' + name + ' Mc' + adj + ' pants';  
};  
var returnResults = nameImprover('preston','purple');  
returnResults; //'Col preston Mcpurple pants'  
//Side Effects:  
var instructorName = 'preston';  
var sideEffectImprover = function(adj) {  
  instructorName = 'Col ' + instructorName +   
    ' Mc' + adj + ' pants';  
};  
var sideEffectResults = sideEffectImprover('purple');  
sideEffectResults; //undefined  
instructorName; //'Col preston Mcpurple pants'  
```  

WHY USE SIDE EFFECTS?  

```javascript
var logResults = console.log('side effects are useful');  
logResults; //undefined  
var addUserToDatabase = function(username, userObj) {  
  if(database[username] === undefined) {  
    database[username] = userObj;  
  }  
};  
//note that we are not returning anything here.   
//we don't want to return the entire database  
//and we already have the userObj since we had it  
//to pass into addUserToDatabase.  
//The function is clearly still useful, even though  
//it doesn't return anything.  
```  

RETURN ENDS FUNCTION  

```javascript
var totallyHarmless = function() {  
  return 'world peace';  
  launchAllNuclearMissiles();  
};  
totallyHarmless(); //returns 'world peace'  
//does not invoke launchAllNuclearMissiles  
  //because that comes after the return statement  
  //and return statements immediately stop the  
  //function and end it.  
```  

TUNNEL- RETURN  
Since a function creates it's own local scope, the global* scope can't see anything that's going on inside that function body.   
The return value is the one way for the outside world to 'tunnel into' the function and see something that's going on.   
We can use side effects to save the work that a function that has done for us into a variable that's accessible in the global scope.   
Or, we can return a value, directly communicating the results to whatever we have in the global scope that's listening for the results of the function.   

```javascript
var testArr = [1,2,3,4];  
var globalSum = 0;  
var sumFunc = function(arr) {  
  for (var i = 0; i < arr.length; i++) {  
    globalSum += arr[i];  
  }  
  return 'string from sumFunc';  
};  
var returnVal = sumFunc(testArr);  
console.log(globalSum); //10  
console.log(returnVal); //'string from sumFunc'  
```  

Returned Values (function output)  
* whatever appears after the "return" keyword gets evaluated then provided as output when the function gets invoked.  
* return exits out of the function, code that comes after doesn't get run  
* default return value is undefined  
Side Effects
* when something outside of the function scope gets affected. Examples:  
 * a variable in an outer scope gets changed  
 * browser actions - console.log, alert, prompt  

NESTING  

```javascript
var box = {};  
box.innerBox = {};  
box.innerBox.innerInnerBox = {};  
// or...  
box['innerBox'].innerInnerBox = {};  
// or...  
box['innerBox']['innerInnerBox'] = {};  
// or...  
var box = {  
  innerBox : {  
    innerInnerBox : {}  
  }  
};   
```


## Control Flow  
 * Code doesn't always run from line in sequence to the last line.  
 * Some lines run more than once when in loops.  
 * Some lines get skipped due to conditional statements.  
 * Code makes choices where it will execute.  

### Iteration Loops  
 * Loops allow us to take a look at each of the properties inside of our storage objects.    
 * Within the loop we can do the normal property access and assignment stuff.  
 * Arrays and Objects each get their own special for loop.  

```javascript
//ARRAYS  
for( var i = 0; i < arr.length; i++) {  
 //do things...  
}    
//OBJECTS  
for( var key in obj) {  
 //do things...  
}   
```  

### Array for loops  
 * Arrays are numerically indexed.  
```javascript
 var arr = ['car','truck','bus'];  
 for( var i = 0; i < arr.length; i++) {
  //this is the body of the loop
  //the code in here gets executed once
    //for each iteration
 }
```  
**INITIALIZATION**
*i* is just a number.  
The index that we want to start at (often 0)  
**CONDITION**    
As long as condition is true, we continue with the loop.  
Once it is no longer true, the loop ends.  
**FINAL EXPRESSION**    
This is the amount by which 'i' changes each time the body of the loop is run.     
Often we simply increment by 1.  

```javascript  
var arr = ['pirate','unicorn','dragon'];
for( var i = 0; i < arr.length; i++) {
  console.log('the valued stored at
    the ' + i + 'th position of the array
    is: ' + arr[i]
  );
}
```  



### Object for loops  

```javascript  
 var obj = {occupation: 'creature dweller',  
  steed: 'lizard',  bestFriend: 'pygmy hippo'};  
 for( var key in obj ) {
   console.log('the value stored at ' + key
   + ' is: ' + obj[key]);  
 }
```
### LOOPS SUMMARY  
* Use loops when you need to access all of the properties in a collection
* For arrays always use the for-with-semicolons loop for
 * (var i=startIndex; i<arr.length; i=i+increment) { ... }  
 * Order is guaranteed because you are explicitly specifying the indices to check.  
 * For objects always use the for-in loop.  
  * for (var key in obj) { ... }
  * Order is not guaranteed

## If Statements  

```Javascript
var alwaysFalse = false;  
if(alwaysFalse) {  
  //this code is never executed  
} else {
  //this code is executed if the condition is false  
}  
```  

#### IF Statements Summary  
1. if statements to run code only if a conditional statement is true  
2. Use optional else if statement to check multiple conditions one after another  
3. Use else block to execute code if none of the conditionals evaluate to true  

#### Conditionals Summary  
1. conditional statements always evaluate to true or false  
 1b. values that are not true/false get converted based on their truthiness/falsiness
 1c. if you need to do an equality comparison, always use '===' / '!==' rather than '==' / '!='  
2. chain boolean expressions using && and/or ||  
3. logical NOT operator (!) converts the following expression to a boolean and then   4. returns the opposite boolean value (ex: !null returns true)  
  tip: use !! to see if something is truthy or falsey (ex: !!null returns false)
