---
layout: post
section-type: post
title: Journey Into Javascript Algorithms - Sets
categories: ['programming']
tags: [ 'javascript','algorithms']
---

# Javascript 

![Javascript](/img/js.png)  

## Javascript Algorithms - Sets

-- Sets are a data structure of unordered lists of related elements where each element is unique.  
A set with zero elements is referred to as a null set.  

### Sets:  

##### Using Sets 

The two most common methods for basic stack operations are union, intersection and difference.    

The union operation is when a new set is created by combining all the elements of one set with those of another set.      

The intersection operation is when a new set is created by adding all the elements of one set that also exist in the second set.  

The difference operation is when a new set is created by adding all elements of one set except for those elements which exist in the second set.  

The javascript set is represented by using an object whilst the values are object properties. Size is kept as a seperate variable.  

This is just one way of implementing sets via javascript, but there are other ways too.  

```javascript
function jsSet(){
    this.set = {}; //initialise an empty object
    this.size = 0; //initialise the size starting at 0
}

```  

#### Adding items to the set  

The first check looks to see if the data exists in out set, using the hasOwnProperty method used for js objects.  
Assuming the data is not present then we simply add the data value by setting the property of the object to the data passed in to the add function.  
Here we are setting the value to be true but it could be anything.  

```javascript
jsSet.prototype.add = function(data){
    if (!(this.set.hasOwnProperty(data))){
        this.set[data] = 'true';
        this.size++;
    }
}

```  

#### Removing items from the set  

```javascript
jsSet.prototype.add = function(data){
    if (!(this.set.hasOwnProperty(data))){
        this.set[data] = 'true';
        this.size++;
    }
}

```  


ES6 - includes a native set object. It is now being used in browsers and will soon have full support.  
It would be a best practise to start using the ES6 set structure.  
An advantage of this set object is that it force all keys to be a string like the object does, so keys of 10 and "10" act as seperate keys.  


Next we will look at Javascript sets.
