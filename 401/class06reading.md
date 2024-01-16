# Ten Thousand Game 1

An intro to the random module and risk analysis.

## Reading

[How to use Random Module](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)

[What is Risk Analysis](https://www.edureka.co/blog/risk-analysis-in-software-testing/)

[Test Coverage](https://martinfowler.com/bliki/TestCoverage.html)

## Videos

[Big O Notation](https://www.youtube.com/watch?v=v4cd1O4zkGw)

## Bookmark and Review

[Python Random](https://docs.python.org/3/library/random.html)

## Further Reading

[What is Dependency Injection](https://www.freecodecamp.org/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it-7578c84fa88f/)

## Reading Questions

**How can the random module be utilized in Python to generate random numbers or make selections from a list, and what are some common functions available within the module?**

>*`randint()` - used to generate random integer. Takes two parameters: low end and high end of the range a user sets for the integer to fall between.*
>*`random()` - used to generate a random number between 0 and 1. Can be combined with a random integer or multiplied by another number such as 10 to give a larger range of float numbers.*
>*`choice()` - used to choose a random element from a collection such as a list. Takes the collection object as a parameter.*
>*Other common random module functions include `choices()`, `shuffle()`, and `randrange()`

**In the context of software development, what is risk analysis, and what are the key steps involved in conducting a risk analysis for a software project?**

>*Risk analysis is a systematic process used to identify risks presented by software applications. The common risk analysis steps include (1) Risk Identification (described as "searching the risk" in the reading), (2) Risk Assessment (described as "Analyzing the impact of each individual risk"), (3) Risk Response (described as "Measures for the risk identified")*

**What is test coverage and why is it an important (or potentially misleading) metric in software testing?**

>*Test coverage is a metric provided by a module in pytest measured as a percentage. I don't know what it is measuring exactly, but generally speaking higher numbers correlate with more comprehensive testing of code. It can be misleading because even 100% coverage can still miss some test cases where the code would not provide the intended output.*

**What is Big O notation, and how is it used to describe the performance of an algorithm? Give an example of an everyday task (not software related) that demonstrates O(n) time complexity.**

>*Big O notation is a way to represent the trajectory of growth in a problem's time and space/memory allocation required as the size of the input, represented as "n" grows. A real life example of an O(n) time complexity problem is folding T-shirts. Each T-shirt takes the same amount of time to fold. As the number of T-shirts in the laundry pile (n) increases, the total time required to fold those shirts increases proportionally.*

## Things I want to know more about

>*The random module looks to be pretty expansive. I'd like to spend more time reading about some of the functions I didn't mention above.*
