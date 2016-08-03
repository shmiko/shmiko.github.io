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

You could use an array but we will be using an object represent out set.  
Using an object also enforces uniqueness as object in javascript do not allow different properties on the same key.  

The set class in ES6 includes the following methods:  
add(value). Adds the value to the set.  
remove(value). Removes the values from the set.  
has(value) Returns true if the value exists otherwise false.  
clear(). Removes all items from the set.  
size(). Returns how many items the set contains.  
values(). Returns an array of all items in the set.  



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

First we check that the data to be removed exists in the set by using the same hasOwnProperty as when adding.  
If the property exists then we simply delete the data from the set, when doing this the size is decremented also.  

```javascript
jsSet.prototype.remove = function(data){
    if (this.set.hasOwnProperty(data)){
        delete this.set[data];
        this.size--;
    }
}

```  


#### Testing  

```javascript

    var testMySet = new jsSet();
    testMySet.add(1);
    testMySet.add(2);
    testMySet.add(3);
    console.log('print testMySet ',testMySet);
    console.log('removing 2');
    testMySet.remove(2);
    console.log('print testMySet ',testMySet);

    // print testMySet  jsSet { set: { '1': 'true', '2': 'true', '3': 'true' }, size: 3 }
    // removing 2
    // print testMySet  jsSet { set: { '1': 'true', '3': 'true' }, size: 2 }

```  

#### Checking if data exists in the set  

To determine if a value exists in the set we continuey using the same hasOwnProperty as when adding and removing.  

```javascript
jsSet.prototype.exists = function(data){
    if (this.set.hasOwnProperty(data)){
        return true;
    } else {
        return false;
    }
}

```  

//tests

#### Union of two sets    

The union of two sets returns a new set with all elements from each of the original sets.    

```javascript
jsSet.prototype.union = function(setTwo){
    var unionSet = new jsSet();
    for (var key in this.set){
        if (this.set.hasOwnProperty(key)){
            unionSet.add(key);
        }
    }
    for (var key in setTwo.set){
        if (!unionSet.set.hasOwnProperty(key)){
            unionSet.add(key);
        }
    }
    return unionSet;
}

```  

#### Intersection of two sets    

The intersection of two sets returns a new set with elements that exist in both of the original sets.    

```javascript
jsSet.prototype.intesect = function(setTwo){
    var interSet = new jsSet();
    for (var key in this.set){
        if (setTwo.set.hasOwnProperty(key)){
            interSet.add(key);
        }
    }
    return interSet;
}

```  

ES6 - includes a native set object. It is now being used in browsers and will soon have full support.  
It would be a best practise to start using the ES6 set structure.  
An advantage of this set object is that it force all keys to be a string like the object does, so keys of 10 and "10" act as seperate keys.  


Next we will look at Javascript dictionaries.
