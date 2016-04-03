---
layout: post
section-type: post
title: Journey Into Javascript Callbacks and Closures
categories: ['programming']
tags: [ 'javascript']
---


## Javascript Callbacks(HOF), Anonymous Function Params And Closures  

-- Callbacks also known as Higher Order Functions   

-- Passing anonymous functions as parameters 

-- Closure - Callbacks are closures   


### Callbacks:  

##### Using Callbacks 

```javascript
function testCallback(num,callback){
	console.log('Hello ');
	callback();
};

testCallback(7, callbackTest2);

function callbackTest2(){
	console.log('Paul - I am the callback!');
};

function writeMySkills(myData) {
    if ( typeof myData === "string")
    {
        console.log(myData);
    }
    else if ( typeof myData === "object")
    {
        for (var item in myData) {
            console.log(item + ": " + myData[item]);
        }
    }
};
function getMyInput(options, callback) {
	var allMyData = [];
    allMyData.push(options);
    callback(options);
}
getMyInput({name:"Paul", skills:"JavaScript"}, writeMySkills);
```


##### Passing Anonymous functions as parameters  

```javascript

var testArray = [29, 15, 31, 101, 96, 77, 4, 19, 1];

function isPrime(number) {
    var start = 2;
    while (start <= Math.sqrt(number)) {
        if (number % start++ < 1) return false;
    }
    return number > 1;
}

distillPrimes = function(collection, callback, number){
	number = number || 0;
    console.log('number:',number)
    toolbelt.loop(collection, function(num,ind){
        if(callback(num,ind)){
            number = number + num;
            console.log(number,num);
        }

    })
    return number;
};

var testDistillPrimes = distillPrimes(testArray, function(startNumber,ind){
   return isPrime(startNumber);
});
```  


#####  Closures 

```javascript
// Global Scope starts under here 
function aFavoriteSuperhero () {  // Establish dummy global scope functions to return some words so the function calls in local scopes work
	return "BananaMan";
}
function aFavoriteVillain () {
	return "BlenderMan";
}
function aFightBetweenGoodAndBad () {
	return " Traps ";
}

var Superhero = aFavoriteSuperhero();
var newDoIt = function() { // <-- scope1 starts here
	var favoriteVillain = aFavoriteVillain();
	var doIt = function() { // <-- scope2 starts here 
		var Task = aFightBetweenGoodAndBad();
		console.log(Superhero+Task+favoriteVillain);
	}; // <-- scope2 ends here 
	doIt();
	// -> BananaMan Traps BlenderMan
	doIt();
	// -> BananaMan Traps BlenderMan
}; // <-- scope1 ends here
newDoIt();
// -> BananaMan Traps BlenderMan
newDoIt();
// -> BananaMan Traps BlenderMan

```
