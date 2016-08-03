---
layout: post
section-type: post
title: Journey Into Javascript Algorithms - Queues
categories: ['programming']
tags: [ 'javascript','algorithms']
---

# Javascript 

![Javascript](/img/js.png)  

## Javascript Algorithms - Queues

-- Queues are a FIFO, First In First Out list type data structure.  
A queue is a linear collection, items are added at the end and are removed from the front.  
Queues support three basic operations; insert, remove and look. 

### Queues:  

##### Using Queues 

The two most common methods for basic stack operations are insert and remove.  

The push operation is exactly the same native function used for adding an element into a queue.    

The native JS operations supported are
Push is used to insert an element into the queue.  
Shift is used to extract an element form the queue.  

Writing your own functions can overcome some speed issues inherint with the shift function as it changes the array each time a change is made.  
Implementing your own cleanup up unused array space at regular intervals is a more performant way to work with javascript queues.  

Queue items will be stored in an array, head will be used to track the top or head of the queue, for every element removal we will return the element referenced by the head and then increment the head to point to the next item in the queue.  

We will have a enqueue and dequeue function for each operation.

```javascript
function queueOfShoppers(){
    this.head = 0; //Initialised to 0 to indicate the position of the first item, assuming the array contains 1 item.  
    this.data = []; //Initialised as an empty array.
}

//building the enqueue function
queueOfShoppers.prototype.enqueue = function(data){
    this.data.push(data);
}

//building the dequeue function - there will be some memory leak associated with this function, we will discuss this shortly.  
queueOfShoppers.prototype.dequeue = function(){
    if (this.head < 0 || this.head >= this.data.length){
        return null;
    }
    var dequeuedItem = this.data[this.head];
    this.head++;

    return dequeuedItem;
}

//Having a look at which is the item at the front of the queue, similar to the dequeue function but the head doesn't move to the enxt item.  
queueOfShoppers.prototype.look = function(){
    if (this.head < 0 || this.head >= this.data.length){
        return null;
    }
    return this.data[this.head];
}

//testing the above functions
var queue = new queueOfShoppers();
console.log("enqueue 100");
queue.enqueue(100);

console.log("enqueue 200");
queue.enqueue(200);

console.log('Dequeue: ' + queue.dequeue());
console.log('Dequeue: ' + queue.dequeue());
console.log('Dequeue: ' + queue.dequeue());

//We are rewriting the dequeue function as the original code leaks memeory.  
//The above funtion never releases the array despite it being removed, the array still holds a reference to the item.  
//All the elements in the array at indexes less than the head are garbage.  
//To fix this we cleanup the array, we do not have to slow down for each dequeue, we cleanup at a certain preset threshhold.  

queueOfShoppers.prototype.dequeue = function(){
    if (this.head < 0 || this.head >= this.data.length){
        return null;
    }

    var dequeuedItem = this.data[this.head];
    this.head++;
    //clean out the garbage at 100 items
    if (this.head === 100){
        this.data.splice(0,100);

        //reset the head
        this.head = 0;
    }
    return dequeuedItem;
};


```

Next we will look at Javascript sets.  


