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
Queues support three basic operations; insert, remove and look. 

### Queues:  

##### Using Queues 

The two most common methods for basic stack operations are insert and remove.  

The push operation is exactly the same native function used for adding an element into a stack.    

The native JS operations supported are
Push is used to insert an element into the queue.  
Shift is used to extract an element form the queue.  

Writing your own functions can overcome some speed issues inherint with the shift function as it changes the array each time a change is made.  
Implementing your own cleanup up unused array space at regular intervals is a more performant way to work with javascript queues.  

Queue items will be stored in an array, head will be used to track the top or head of the queue, for every element removal we will return the element referenced by the head and then increment the head to point to the next item in the queue.  

We will have a enqueue and dequeue function for each operation.

```javascript
function queueOfShoppers{
    this.head = 0; //Initialised to 0 to indicate the position of the first item, assuming the array contains 1 item.  
    this.data = []; //Initialised as an empty array.
}

//building the enqueue function
queueOfShoppers.prototype.enqueue = function(data){
    this.data.push(data);
}

//building the dequeue function
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
