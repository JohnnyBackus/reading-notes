# Linear Regressions

Data Week: Intro to Linear Regressions

## Reading

[How to Run Linear Regression in Python](https://www.activestate.com/resources/quick-reads/how-to-run-linear-regressions-in-python-scikit-learn/)

- NOTE: The content to read ends at the `Regression vs Classification`` section. After that it’s a product pitch for ActiveState which is not required, though you may find it interesting.

## Additional Resources

[Linear Regression in Python](https://realpython.com/linear-regression-in-python/)

## Videos

[Introduction to Simple Linear Regressions](https://www.youtube.com/watch?v=KsVBBJRb9TE)

## Bookmark and Review

[Understanding Train Test Split](https://builtin.com/data-science/train-test-split)

[What is Linear Regression](https://www.statisticssolutions.com/free-resources/directory-of-statistical-analyses/what-is-linear-regression/)

## Reading Questions

**Can you explain the basic concept of linear regression and its purpose in the context of machine learning and data analysis?**

>*Linear regression provides a way to measure and describe the strength of a relationship between explanatory/independent and response/dependent variables. In the context of machine learning, the stronger the relationship between variables, the more viable it is for the independent variables to be used to predict the dependent variables and make inferences from future independent variable data.*

**Describe the process of implementing a linear regression model using Python’s Scikit Learn library, including the necessary steps and functions.**

>*Taken directly from the Real Python link above:*

```
1. Import the packages and classes that you need.
2. Provide data to work with, and eventually do appropriate transformations.
3. Create a regression model and fit it with existing data.
4. Check the results of model fitting to know whether the model is satisfactory.
5. Apply the model for predictions.
```
>*For step 3 above, you create the model using the LinearReferession() class. The .fit() method is used for calculating regression coefficients.*
>*For step 4, obtain the coefficient of determination using the .score() method*

**What is the purpose of splitting the dataset into train and test sets, and how does this contribute to the evaluation of a machine learning model’s performance?**

>*This process insructs that a programmer use separate data to train and test an MLM. This is advised because an MLM tested with the same data used for training will overfit to the data so that it performs better on tests, and paradoxically perform worse with new data than an MLM that was trained on different data... kinda like a student that only studies to pass the tests may actually understand a topic less well than another student who studies the subject matter more broadly, but does less well on the exam.*

## Things I want to know more about

>*MLM programming is wild... I'd like to learn more about it in general. I heard somewhere that OpenAI has (or will soon have) a store to allow developers to supply their own data to train new AI apps.*
