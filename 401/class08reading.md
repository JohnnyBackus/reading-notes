# Ten Thousand 3

Intro to List Comprehensions and Decorators

## Reading

[List Comprehensions](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

## Audio

[Listen (optional): Debugging with PySnooper](https://www.pythonpodcast.com/pysnooper-python-debugging-episode-241/)

## Bookmark and Review

[Primer on Decorators](https://realpython.com/primer-on-python-decorators/)

## Reading Questions

**What is the basic syntax of Python list comprehension, and how does it differ from using a for loop to create a list? Provide an example of a list comprehension that squares the elements in a given list of integers.**

>*Basic Syntax for Python List Comprehension:* `[ *expression* for *item* in *list* ]`
>*It is functionally similar to a simple for loop, but uses fewer lines of code. An example of a list comprehension that squares the elements in a given list of integers would be:*
```square_list = [ int*int for int in integer_list ]```

**What is a decorator in Python?**

>*A notation `@example_decorator_func` placed above a function to indicate that a decorator function is being called and the function beneath it is being passed as a parameter.*

**Explain the concept of decorators in Python. How do they work, and what are some common use cases for them? Provide an example of a simple decorator function from the reading.**

>*Decorator functions modify other functions so when the orignal function is called later, it will behave as instructed by the decorator function. An example from the reading:*

```from decorators import do_twice

@do_twice
def say_whee():
    print("Whee!")

>>> say_whee()
Whee!
Whee!
```

## Things I want to know more about

>*Thus far print() doesn't feel as user-friendly as console.log(). I would like to find time to learn how to use PySnooper or another debugger.
