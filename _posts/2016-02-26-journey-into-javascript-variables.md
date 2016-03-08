---
layout: post
section-type: post
title: Javascript variables
categories: ['programming']
tags: [ 'javascript']
---


# Journey Into Javascript

## Variables  

- Declaration and assignment
- Referencing primitive values
- Variables rules
- Good naming conventions
- Bad naming conventions
- Example use cases

**Variable Declaration**  
//Proper Declaration  
> var name = 'Stevie Nicks';  
> var song = 'Edge of Seventeen';  

var name is the *Declaration*  
'Stevie Nicks' is the *Assignment*  

//Never Use
> newName = 'Eddie Money';  
> newSong = 'take me home tonight';  

This is a Bad convention: 'new___'

//Don't Use ( for now )
> window.newername = 'Charlie Parker';  
> window.newerSong = 'Early in the morning';

**Rules and Conventions**  
Declare and assign at the top of your scope/code
> var favBand = 'Earth,Wind and Fire';  
> var favSong = 'Fantasy';  
> console.log(favBand, favSong);  

Good Examples ( Declarations Only )  
> var songsArray; //Descriptive of the reference  
> var artistName; //Single word  
> var templeOfTheDog; //'camelCase': hungryHungryHungry  

Bad Examples ( Declarations Only )  
> var SongTitles; //Start with lowercase  
> var tracknumber; //Use camelCase  
> var newArray; //Of What?  
> var &no$yb@ls; // Code will break  

// Words not to use ( your code will break ):  
// > var new, var, in, function, String, Number, break, typeof...  
// Basically, If your editor highlights the word, don't use it!  

> var firstName = 'David'; //Slot 1  
> var lastname = 'Bowie'; //Slot 2  
> firstNameAgain = firstName; //Slot 3  

What is Javascript doing?  
> firstName = 001;  
> lastname = 002;  
> firstNameAgain = 003;    

*Variable Usage*  

//Proper Declaration  
> var firstName = 'Stevie';  
> var lastname = 'Wonder';  

//We want his full name  
> firstName + lastName; // 'Stevie' + 'Wonder' = 'StevieWonder'

//Fix the formatting
> firstName + ' ' + lastname; // 'Stevie' + ' ' + 'Wonder' = 'Stevie Wonder'  

//Print the fullName
> console.log(fullname); //???  Reference Error  

//Declare before using
> var fullname = 'Scott Weiland';  //001
> var firstname = fullname.split(' ')[0]; //002  

> console.log(fullname); //'Scott Weiland'  001
> console.log(firstname); //'Scott'  002

//What's going to happen?
> console.log(stoneTemplePilots); //undefined  

'Declared' or 'namespaced' but not 'defined' before it's used.  
Hence 'undefined'
> var stoneTemplePilots = fullname; // 'Scott Weiland' - Makes a copy for 'primitive' types  003  

//Overwriting  
> var fullName = 'Stone Temple Pilots'; // 004
> console.log(fullname); // 'Stone Temple Pilots' 004

**Variables - Key takeaways**
- Variables allow us to re-use values  
- They just point to a value in memory  
- Values don't depend on them, we do  
- Use good, descriptive names  
- What is an 'undefined' variable  
- Declare variables before using them  
- Always use the 'var' keyword when declaring  

**Vocabulary**  
- Declaration  
- Assignment  
- Hoisting  
- namespace  
