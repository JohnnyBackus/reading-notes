# More Readings: HTML Lists, Control Flow with JS, and the CSS Box Model

A little more detail regarding how we can apply style and function to our websites.

## HTML: Lists

**When should you use an `unordered list` in your HTML document?**

>*When sequencing or rank ordering is not important.*

**How do you change the `bullet style` of unordered list items?**

>*You can add an attrribute to your HTML tag, but you will have more options and cleaner code if you apply the CSS property `list-style-type`*

**When should you use an `ordered list` vs an `unordered list` in your HTML document?**

>*If the order in which you present your list items is important, you should use an ordered list. An example might be a set of chronological instructions or ranking of the best fried chicken sandwiches in Portland.*

**Describe two ways you can change the numbers on `list items` provided by an `ordered list`**

>*You can use the `type` attribute within the HTML element, or you can apply the CSS property `list-style-type`.*

## CSS: The Box Model

**Describe the CSS properties of `margin` and `padding` as characters in a story. What is their role in a story titled: “The Box Model”?**

>*Padding is grieving. For her, that process is to push others away.. maybe 20 or 30 pixels even. It seems lonely, and her friends want to help. But, Padding knows she needs space. So much so that she sequesters herself in the most inner room of her home. There she still hears the pleading knocks at her door and rapping of well-meaning friends upon her window panes. It's all too much. Luckily her neighbor Margin gets it and shooes the neighbors away a reasonable and aesthetically pleasing distance. The end. Characters in this abstract story were Content played by Padding's emotions. Border played by the house's walls. Other CSS boxes played by the neighbors. And finally, Padding and Margin played by themselves.*

**List and describe the four parts of an HTML elements box as referred to by the `box model`.**

>*Well, you got some `content`. Then you wrap around it some `padding` as a buffer between the content and your `border`. Oh right... the `border` is like a shell around the content and it's padding. You can style it if you like with colors or make it dashed and whatnot. You can also adjust its thickness, too. Surrounding the border is the `margin`. It's not really a part of the box... more like designated space to keep the box from getting too close to other CSS boxes or perhaps the edge of the page.*

## JS: Arrays, Operators, Expressions, Conditionals, and Loops

**What `data types` can you store inside of an `Array`?**

>*I'm no sure if this list is exhaustive, but per the assigned reading, we can store strings, numbers, objects, and other arrays.*

**Is the `people` array a valid JavaScript array? If so, how can I access the values stored? If not, why?**  
    const people = [['pete', 32, 'librarian', null], ['Smith', 40, 'accountant', 'fishing:hiking:rock_climbing'], ['bill', null, 'artist', null]];  
  
>*Yes it is. You can access specific values via their index or you access the whole array at once with the command `console.log(people)`... this seems to get much more complicated if you want to see what's inside the nested arrays all at once, though. ChatGPT suggests a scary-looking loop*

**List five shorthand operators for assignment in javascript and describe what they do.**

>*Shorthand operators save a few spacebar keystrokes. In the examples below, the shorthand operators are to the left of the `==`. On the right is the longform equivalent. In these examples, you are also saved from having to type 'x' twice. When 'x' is something much longer in character length, you save a lot more keystrokes.*

- *addition* `x += y == x = x + y`  
- *subtraction* `x -= y == x = x - y`  
- *multiplication* `x *= y == x = x * y`  
- *remainder* `x %= y == x = x % y`  
- *logical AND* `x &&= f() == x && (x = y)`  

**Read the code below and evaluate the last `expression` and explain what the result would be and why.**  
    let a = 10;`  
    let b = 'dog';  
    let c = false;  

    // evaluate this  
    (a + c) + b;`  

>*I got help from ChatGPT on this one to figure out what to do with the `false` part. `false` is evaluated as 0, so I beleive the rest is pretty straight forward order of operations arithmetic and then string concantenation. 10+0 = 10. 10 + dog concantenates to '10dog'*

**Describe a real world example of when a conditional statement should be used in a JavaScript program.**

>*The example in our lab today was in order to provide different alerts to different user inputs.*

**Give an example of when a Loop is useful in JavaScript.**

>*One way a loop can be used is to repeat executing a piece of code until a certain condition is met. For example, prompting a user for their password until they enter it correctly or exceed the maximum number of allowed attempts.*

## Things I want to know more about

*Arrays seem pretty cool.*
