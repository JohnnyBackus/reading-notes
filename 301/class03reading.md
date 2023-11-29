# Passing Functions as Props

Description

## React Docs - lists and keys

**What does .map() return?**

>*An array of the same length as the array it modifies.*

**If I want to loop through an array and display each value in JSX, how do I do that in React?**

>*You could use the `.map()` method to change each item into markup that can be displayed on a website such as a list item, paragraph, or table cell.*

**Each list item needs a unique ____.**

>*key*

**What is the purpose of a key?**

>*A key is used to distinguish a list item from its siblings.*

## The Spread Operator

**What is the spread operator?**

>*I read the mdn web docs explanation... not sure I quite get it, but it looks like a form of shorthand that can be used in place of writing each individual expression of an array (or other "iterable") that you may want to pass to a function, array, or object.*

**List 4 things that the spread operator can do.**

>*1. It can be used to pass arguments into a function*
>*2. It can be used to combine two arrays into one*
>*3. It can be used to conditionally add an item to an array*
>*4. It can be used to merge objects*

**Give an example of using the spread operator to combine two arrays.**

>const array1 = [a, b, c, d];
>const array2 = [e, f, g, h];
>const array3 = [...array1, ...array2];

**Give an example of using the spread operator to add a new item to an array.**

>*Not sure if this is the answer we're looking for, but since the spread operator can be used to concatenate arrays, we could add a new item to an array if that item is in it's own array. We could also add an item conditionally using a condional operator. For example:*
>let array = [1 , 2, 3];
>const wantFour = true;
>array = [...array, ...(wantFour ? [4] : [])];

**Give an example of using the spread operator to combine two objects into one.**

>const summerExtremes = {maxTemp: 99, minPrecip: 0.5};
>const winterExtremes = {minTemp: 29, maxPrecip: 14};
>const yearlyExtremes = {...summerExtremes, ..winterExtremes};

## How to Pass Functions Between Components

**In the video, what is the first step that the developer does to pass functions between components?**

>*The developer defines the two components and the function within the parent component*

**In your own words, what does the `handleClick` function do?**

>*It registers a click of the button by logging "parent click" in the console*

**How can you pass a method from a parent component into a child component?**

>*You can return the child component with a property you define as the function you wish to pass. In the video, the developer defines a property of the Child called handleClick as the function handleClick: handleClick={handleClick}*

**How does the child component invoke a method that was passed to it from a parent component?**

>*The child component can invoke a function passed to it by using curly braces with the function name inside. In the video example, the function is invoked with {handleClick}*

## Things I want to know more about

>*I wonder if {handleClick} could be replaced by props.handleClick in the video example.*
