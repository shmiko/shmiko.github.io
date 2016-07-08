---
layout: post
section-type: post
title: Journey Into Javascript Algorithms - Stacks
categories: ['programming']
tags: [ 'javascript','algorithms']
---

# Javascript 

![Javascript](/img/javascript.png)  

## Javascript Algorithms - Stacks

-- Stacks are a LIFO, Last In First Out list type data structure.  
Think of a stack of books in terms of accessing the first book in a stack of 10 books, you would need to remove the last 9 to get to the first book.  

### Stacks:  

##### Using Stacks 

The two most common methods for basic stack operations are push and pop.  

Push is used to insert an element into the stack.  
Pop is used to extract an element form the stack.  

Keeping track of the top most element is important, when we push an element the top is updated to reflect the most recent element added, likewise when we pop an element the top is also updated to reflect the next most recently added element.  

```javascript
function stackOfBooks{
    this.top = -1; //Initialised to -1 to indicate no elements
    this.value = []; //Initialised as an empty array.
}

//not using the array push function yet
stackOfBooks.prototype.push = function(book){
    this.top++;
    this.value[this.top] = book;
}

//not using the array pop function yet
stackOfBooks.prototype.pop = function(){
    if (this.top < 0){
        return null;
    }
    var topBook = this.value = this.value[this.top];
    this.top--;

    this.value.length--;

    return topBook;
}

//Having a look at which is the top book
stackOfBooks.prototype.look = function(){
    if (this.top < 0){
        return null;
    }
    return this.value[this.top];
}

//testing the above functions
var stack = new stackOfBooks();

for (var i = 0; i <= 20; i++){
    console.log('Push ', i);
    stackOfBooks.push(i);
}

//Looking looking looking...
console.log('Last book is ', stack.look());

//Poping last book added
console.log('Pop last book', stack.pop());



```
