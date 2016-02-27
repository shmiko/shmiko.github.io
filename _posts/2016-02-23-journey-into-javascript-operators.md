---
layout: post
section-type: post
title: Javascript Operators
category: javascript
tags: [ 'javascript']
---


# Journey Into Javascript

## Basic Data types, Operators and Values

### Operators
**Mathematical**
- Addtion - ( + )
- Subtraction - ( - )
- Multiplication - ( * )
- Division - ( / )
- Modulus - ( % )
- Increment - ( ++ )
- Decrement - ( -- )
- Greater than - ( >,>= )
- Less than - ( <,<= )

**Access/Assign**
- Brackets - ( [] )
- dot - ( . )
- Assignment - ( = )
- Assignment - ( += )
- Assignment - ( -= )

**Keywords**
- var
- function
- for
- in
- typeof
- this
- new

**Comparison**
- Equality ( === )
- Not Equal ( !== )

**Logical**
- And - ( && )
- Or - ( || )
- Not - ( ! )

**Other**
- Grouping - ()
- Ternary - ( ? )

**Ignore**
- ( == )
- ( != )

### Operator Types
**Mathematical**
- Addition - ( + )
  *Example* > 5 + 4; //Self Explanatory   
  Can also be used to join text > 'I want to go' + ' home!';  
  And also to join text to numbers or variable etc > 'Give me ' + 500 + 'dollars now...';  
  Often seen in logging to the console.
- Modulus - ( % ) > 15 % 4; //Modulus, gets the remainder

**Comparison**
- Equality - ( === )  
  *Example* > 1000 === 1000; //True    
  \> 'Sussudio' === 'Sussudio'; //True
- Not Equal - ( !== )  
  *Example* > 5000 !== 5000; //False  
  \> 'Basketball' !== 'and Mr. Curtis Blow'; //True


**Access/Assign**
- Brackets - ( [] )
- dot - ( . )
- Assignment - ( = )

**Keywords**
- typeof  
*Example*
\> typeof 'Do the Beat Street Strut!'; //string    
\> typeof { startlight: 'starbright' }; //object   
\> typeof 8675309; //number    
\> typeof function() {}; //function    
*Don't worry about:*
 Ignore
 - ( == )
 - ( != )
 Do Not use these...

*Assignment Operator* //Not equals is !==
> var planet = 'rock!'; //in memory is "rock!"
> ['Don\'t', 'stop', 'the', planet][3]; //in memory is "rock!"
> ['do', 'the', 'conga'][3] = 'beat'; // in memory is ['do', 'the', 'conga', 'beat']

*Objects*
> { }['first'] = 'Gloria'; // in memory is {"first":"Gloria"}
> { first: 'Gloria' }.last = 'Estefan'; // in memory is {"first":"Gloria","last":"Estefan"}
> { music: 'is gonna get you!' }['music']; // in memory is "is gonna get you!"
