---
layout: post
section-type: post
title: Journey Into Javascript Algorithms - Queues
categories: ['programming']
tags: [ 'javascript','algorithms']
---

# Javascript 

![Javascript](/img/javascript.png)  

## Javascript Algorithms - Queues

-- Queues are a FIFO, First In First Out list type data structure.  
A queue is a linear collection, items are added at the end and are removed from the front.  
Queues support three basic operations, insert, remove and look. 

### Queues:  

##### Using Queues 

The two most common methods for basic stack operations are insert and remove.  

The push operation is exactly the same native function used for adding an element into a stack.    

The native JS operations supported are
Push is used to insert an element into the queue.  
Shift is used to extract an element form the queue.  

Keeping track of the top most element is important, when we push an element the top is updated to reflect the most recent element added, likewise when we shift an element the top is also updated to reflect the next most recently added element.  

```javascript
function queueOfShoppers{
    this.top = -1; //Initialised to -1 to indicate no elements
    this.value = []; //Initialised as an empty array.
}

//not using the array push function yet
queueOfShoppers.prototype.push = function(book){
    this.top++;
    this.value[this.top] = book;
}

//not using the array pop function yet
queueOfShoppers.prototype.pop = function(){
    if (this.top < 0){
        return null;
    }
    var topBook = this.value[this.top];
    this.top--;

    this.value.length--;

    return topBook;
}

//Having a look at which is the top book
queueOfShoppers.prototype.look = function(){
    if (this.top < 0){
        return null;
    }
    return this.value[this.top];
}

//testing the above functions
var stack = new queueOfShoppers();

for (var i = 0; i <= 20; i++){
    console.log('Push ', i);
    queueOfShoppers.push(i);
}


//Looking looking looking...
console.log('Last book is ', stack.look());

//Poping last book added
console.log('Pop last book', stack.pop());

//Looking looking looking...
console.log('Last book is ', stack.look());

//Poping last book added
console.log('Pop last book', stack.pop());

//Looking looking looking...
console.log('Last book is ', stack.look());


//pushing another book
console.log('New book is 100 ');
stack.push(100);

//Looking looking looking...
console.log('Last book is now ', stack.look());


```
