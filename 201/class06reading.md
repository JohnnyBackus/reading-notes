# Problem Domain, Objects, and the DOM

A first look into object-oriented code.

## JavaScript Object Basics

**How would you describe an object to a non-technical friend you grew up with?**

>*An `object` is a collection of information about something.*

**What are some advantages to creating object literals?**

>*It allows you to hold several pieces of related information in one place, which can now be associated to each other by refering to a single object.*

**How do objects differ from arrays?**

>*Arrays are list of single expressions, whereas objects are lists of key-value pairs.*

**Give an example for when you would need to use bracket notation to access an object’s property instead of dot notation.**

>*If you create a variable using an object property, bracket notation allows you to refer to the value of that variable directly.*

**Evaluate the code below. What does the term `this` refer to and what is the advantage to using `this`?**  
  const dog = {
  name: 'Spot',
  age: 2,
  color: 'white with black spots',
  humanAge: function (){
    console.log(`${this.name} is ${this.age*7} in human years`);
  }
 }

>*`this` is a keyword that pulls the value of the property being referred to within this specific object `dog`. It is important when you have a `method`/`function` that is going to be applied to multiple objects.*

## Introduction to the DOM

**What is the DOM?**

>*DOM = Document Object Model.*

**Briefly describe the relationship between the DOM and JavaScript.**

>*The DOM runs JavaScript within the browser to manipulate the webpage.. I think?*

## Miscellaneous

**What's the difference between primitive values and object reference in JavaScript?**

>*Primitive values are single pieces of data that can be stored variables. Object reference does not reference single pieces of data directly, but refers to a key-value pair within an object... and then my brain starts to explode.*

## Things I want to know more about

*I think I want better understand objects?*
