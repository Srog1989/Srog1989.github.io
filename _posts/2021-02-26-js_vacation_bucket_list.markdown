---
layout: post
title:      "JS Vacation Bucket List"
date:       2021-02-26 16:40:23 -0500
permalink:  js_vacation_bucket_list
---

Wow, here I am completing my Mod 4 project. This Mod introduced me to the Javascript world. It's been such a big transition from ruby! My head has been spinning throughout this modules coursework, but the challenge has been a great learning experience. I always feel like I learn the most during the 2 weeks of project mode, so I always enjoy the process.

Our projects required us to create a single page application using a rails backend API to fetch JSON data from.  I chose to create Vacation Bucket List. By using fetch calls, DOM manipulation, HTML, Event Listeners, and of course a little ruby MVC work in the backend,  I was able to have a user interface that allows a user to enter their name to "sign in", and create, read, and delete a destination object to add to their vacation bucket list. It was so different to have everything on one page compared to our rails application where we had a different view and route for each page! 

I could go on and on about my project but,  I'm going to touch base on some key concepts that I personally found to be most important or challenging for me to conceptualize throughtout this module.

**Hoisting**

JavaScript's ability to call functions before they appear in the code is called hoisting. For hoisting to work, the function must be defined using a function declaration. Out of the three typed of JS variables, var, const, and let, var is the only type of variable that can be hoisted. Check out this quick 5 min clip below that greatly explains the concept of hoisting!

https://youtu.be/AplVrrwY1TI

**This**

The JavaScript this keyword refers to the object it belongs to. It has different values depending on where it is used: In a method, this refers to the owner object. ... In a function, this refers to the global object. In a function, in strict mode, this is undefined. I found it fairly easy to take in this concept since it functions very similar to rubys *self method.*

**Arrow Functions**

Was developed to help developers shorten the syntax of their function code. Using arrow functions often appears when using JavaScript's iterator methods. An iterator is a method that allows you to deal with a set of data one at a time.

The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own this, do not have prototypes, cannot be used for constructors, and should not be used as object methods.
```
let sum = (a, b) => a + b;

/* This arrow function is a shorter form of:

let sum = function(a, b) {
  return a + b;
}
```

As you can, see (a, b) => a + b means a function that accepts two arguments named a and b. Upon the execution, it evaluates the expression a + b and returns the result. Always rememberm if there is only one argument, then parentheses around parameters can be omitted.

**JS Variables**

JavaScript has three different keywords to declare a variable. The differences between the three are based on scope, hoisting, and reassignment.

Keyword	Scope	Hoisting	Can Be Reassigned	Can Be Redeclared

**var**	
* scope- Function scope	
* hoisting- Yes	
* can be reassigned- Yes
* can be redeclared- Yes

**let**
* scope- Block scope
* hoisting- No	
* can be reassigned- Yes
* can be redeclared- No

**const**	
* scope - Block scope
* hoisting- No
* can be reassigned-No
* can be redeclared -No

**Variable Scope**

Scope in JavaScript refers to the current context of code, which determines the accessibility of variables to JavaScript. The two types of scope are* local* and *global*:

-**Global** variables are those declared outside of a block

-**Local** variables are those declared inside of a block

In the example below, a *global* variable of species is created. Within the function is a* local * variable with the same name. By sending them to the console, we can see how the variable’s value is different depending on the scope, and the original value is not changed.

```
*Initialize a global variable*
var species = "animal";

function transform() {
*Initialize a local, function-scoped variable*
  var species = "dog";
  console.log(species);
}
*Log the global and local variable*
console.log(species);
transform();
console.log(species);
 
*Output*
animal
dog
animal
```

**Constructor**
So this was pretty cool. A constructor method is  JS version of Ruby's initialize method. It's inside of a class and is used to instantiate an instance of the class, an object.  In JavaScript, a constructor gets called when you declare an object using the new keyword.

```
class Destination {
    static allDestinations = []
    
    constructor(destination){
        this.id = destination.id
        this.city = destination.city
        this.country = destination.country
        this.importance = destination.importance
        this.userId = destination.user_id
       }
		}
		
```


**Promise**

A promise is an object which can be returned synchronously from an asynchronous function. It will be in one of 3 possible states:

1. Pending
2. Fulfilled
3. Rejected

A promise is settled if it’s not pending (it has been resolved or rejected).


All in all, there is so much to take away from the module as a whole, and i'm excited to have Javascript become part of my everyday coding. Moving on to the last and final Module, I'm really  looking forward to what React has to bring to the table! As the saying goes, Learn, Love, Code!







