# FileIO & Exceptions

Reading files and error handling.

## Reading

[Read & Write Files in Python](https://realpython.com/read-write-files-python/)

[Exceptions in Python](https://realpython.com/python-exceptions/)

## Videos

[File Objects - Reading and Writing to Files](https://www.youtube.com/watch?v=Uh2ebFW8OYM)

## Bookmark and Review

[Reading and Writing Files in Python Quiz](https://realpython.com/quizzes/read-write-files-python/)

## Reading Questions

**What is the purpose of the ‘with’ statement when opening a file in Python, and how does it help manage resources while reading and writing files?**

>*It automatically closes the file after use.*

**Explain the difference between the ‘read()’ and ‘readline()’ methods for file objects in Python. Provide examples of when to use each method.**

>*The 'read()' method returns the entire content of a file or a specific number of characters. The 'readline()' method returns one line at a time from the begining. The 'readline()' method can be used in a loop to also go through an entire file, but not occupy as much memory at a time as using the 'read()' method.*

**Briefly describe the concept of exception handling in Python. How can the ‘try’, ‘except’, and ‘finally’ blocks be used to handle exceptions and ensure proper execution of code? Provide a simple example.**

>*Try and except are not disimilar to try and catch we have used previously in Javascript. Both language attempt to run a script and notify the user of any errors encountered without terminating the program. The finally block is optional and will run regardless of whether or not an error is encountered. I've read in a couple resources that this is used for cleanup operations... whatever that means... perhaps closing a file or telling the user "good night"?*

## Things I want to know more about

>*How are 'import' and 'read' different in how they access data and use memory.*
