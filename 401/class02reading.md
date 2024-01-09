# Testing and Modules

Description

## Reading

[In Tests We Trust - TDD with Python](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)

[If name equals main](https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/)

[Recursion](https://www.geeksforgeeks.org/introduction-to-recursion-data-structure-and-algorithm-tutorials/)

## Videos

[What on Earth is Recursion](https://www.youtube.com/watch?v=Mv9NEXX1VHc)

Optional: [Python Modules and Packages Companion Video](https://realpython.com/courses/python-modules-packages/)

## Bookmark and Review

[Google for Education: Python Lists](https://developers.google.com/edu/python/lists)

[Google for Education: Python Strings](https://developers.google.com/edu/python/strings)

[Python Modules and Packages](https://realpython.com/python-modules-packages/)

[Pytest Documentation](https://docs.pytest.org/en/latest/)

[PyTest Tutorial Up to section Running tests in parallel](https://www.guru99.com/pytest-tutorial.html)

## Reading Questions

**What are the key principles of Test-Driven Development (TDD) in Python, and how do they contribute to the overall quality of code?**

>*I read the article, but I thought this response from ChatGPT was easier to read and understand (https://chat.openai.com/share/ee19ce13-7fc8-454f-a229-d49444655d71):*
    Test-Driven Development (TDD) is a software development approach where tests are written before the actual code. This methodology follows a cycle of writing a test, implementing the code to make the test pass, and then refactoring the code as needed. TDD in Python, or any other language, is based on a few key principles that contribute to the overall quality of code:

    1. **Write a Failing Test First:**
    - Start by writing a test that describes a piece of desired functionality.
    - This test should fail initially because the corresponding code has not been implemented yet.

    2. **Write the Minimum Code to Pass the Test:**
    - Write the simplest code that makes the failing test pass.
    - This often involves writing just enough code to satisfy the requirements of the test.

    3. **Refactor the Code:**
    - After the test has passed, refactor the code to improve its design, readability, and maintainability.
    - Ensure that the refactoring does not break any existing tests.

    4. **Repeat the Cycle:**
    - Write another test for the next piece of functionality.
    - Implement the code to make the new test pass.
    - Refactor the code as necessary.

    5. **Automate the Testing Process:**
    - Tests should be automated and run frequently.
    - This ensures that changes to the codebase do not introduce new bugs and that existing functionality remains intact.

    6. **Isolate Units of Code for Testing:**
    - Tests should focus on individual units of code, such as functions or methods.
    - This isolation allows for more targeted testing and makes it easier to identify the source of failures.

    7. **Use Test Doubles (Mocks, Stubs, etc.):**
    - Employ test doubles to isolate the unit being tested from its dependencies.
    - This helps in testing components in isolation and ensures that tests are focused on the specific functionality they are meant to verify.

    8. **Keep Tests Simple and Readable:**
    - Write tests that are easy to understand.
    - Clear and concise tests make it easier for developers to understand the expected behavior of the code and contribute to the overall documentation.

    9. **Test Edge Cases:**
    - Ensure that tests cover a variety of scenarios, including edge cases and boundary conditions.
    - This helps identify and handle potential issues that might not be apparent in normal use cases.

    10. **Continuous Integration (CI) and Continuous Deployment (CD):**
        - Integrate TDD with CI/CD practices to automatically run tests whenever changes are made to the codebase.
        - This ensures that the code remains in a working state and helps catch issues early in the development process.

>*By adhering to these principles, TDD in Python promotes the creation of robust, maintainable, and well-tested code. It encourages developers to think about the design and behavior of their code upfront, resulting in improved software quality and a faster development cycle.*

**Explain the purpose of the `if __name__ == '__main__':` statement in Python scripts. What are some use cases for including this conditional in your code?**

>*This is used to determine if a script is imported as a module or being run as a standalone program. This is useful when writing code that may be used both ways such as for testing.*

**Describe the concept of recursion in Python.**

>*Calling a function within itself... it can kinda operate like nested loops.*

**What is the difference between Python modules and packages? Explain how to create, import, and use them in your Python programs.**

>*Modules are python files that contain code, which will be used repeatedly in a program... for example variables, functions, or classes. Packages are directories of related modules. They must have a `__init__.py` file to distinguish them as packages.*

## Things I want to know more about

>*I don't really get the real world applications of `if __name__ == '__main__':`. Looking forward to seeing how it in action and how we build tests.*
