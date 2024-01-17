# Ten Thousand 2

Variable scope in Python

## Reading

NOTE This is a long reading. Intended area of emphasis is global and nonlocal keywords.

[Python Scope](https://realpython.com/python-scope-legb-rule/)

## Videos

NOTE* The repeated Big O content is intentional. This is a big concept and worth hearing about from multiple presenters. TIP: watch on faster speed if you like.

[Big O notation is simpler than you might think](https://www.youtube.com/watch?v=dNorFNlDbX0)

## Bookmark and Review

[Rolling Dice Examples](https://web.archive.org/web/20220608035657/https://artofproblemsolving.com/wiki/index.php/Basic_Programming_With_Python#Random)

## Reading Questions

**Explain the concept of variable scope in Python and describe the difference between local and global scope. Provide an example illustrating the usage of both.**

>*Variable scope is a language design choice intended to make managing variables a little easier. Local variables exist within a function and are recreated every time a function is called. They are not recognized outside the function, which also means that multiple functions can re-use variable names without affecting operations of each other, because they are all effectively different variables. Global variables are assigned outside of a function and persist. They may be used by multiple functions or scripts.*

**How do the global and nonlocal keywords work in Python, and in what situations might you use them?**

>*The global keyword allows you to use (or create) a global variable inside of a function. Without the global statement, any variable inside of function is local by defualt even if it shares a name with a global variable. Nonlocal keywords behave similarly. They allow the use of a nonlocal variable inside of a nested function... in other words, use of a nonlocal keyword allows for a variable created in the parent function to be used inside of a nested function. Unlike the local keyword, you cannot use the nonlocal keyword to create a variable for use outside of the originating scope.

**In your own words, describe the purpose and importance of Big O notation in the context of algorithm analysis.**

>*Big O notation is a shorthand representation of how resource intensive a function will become relative to the size of the input. Any Big O notation is going to be ok if the data input is very small. However any code that uses Big O(n!) notation should be cause for reconsideration unless we can be certain that the input is going to remain small or we plan to use other strategies such as memoization. Big O(1) is on the opposite end of the spectrum and we can feel pretty confident that any function we right with this notation isn't going to fry our processor.

**Based on the Rolling Dice Example, explain how you would simulate a dice roll using Python. Describe how you would use code to calculate the probability of rolling a specific number (e.g., the probability of rolling a 6) over a large number of trials.**

>*A function to simulate a single roll of a die could look like this:*

```def roll():
    return random.randint(1,6)
    ```
>*The probability of rolling any specific number is going to be the same for all numbers: 1/6 for a single die roll. 1/6 can also be written as (1 - 5/6) wth 5/6 being the odds of rolling something other than your target. I'm not 100%, but I think we can calculate the odds of rolling any number once in n rolls with the formula 1 - (5/6)^n. The function could look like this...*

```def probability_of_rolling(n)
    probability = 1 - (5/6)^n
    return probability
```  

## Things I want to know more about

>*What is Big O? just kidding!*
