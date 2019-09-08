# Week 2
## Reading
- [Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/) (chapters 1-4)
- [Introduction to Programming in Python](https://introcs.cs.princeton.edu/python/home/) (some exercises will be from this book)

## Exercises
### Python brush-up
Solve the following exercises from [Introduction to Programming in Python](https://introcs.cs.princeton.edu/python/home/).

Note: Many of the exercises are asking you to read input from the command line. You may use Jupyter and solve these exercises by defining a function that takes the input as a parameter instead.

- 1.1.1
- 1.2.2, 1.2.5, 1.2.8, 1.2.11
- 1.3.6, 1.3.7, 1.3.13, 1.3.28
- 1.4.2, 1.4.12, 1.4.C2, 1.4.C10
- 2.1.4, 2.1.15, 2.1.16
- 2.3.2, 2.3.C3
- 3.2.1 (without the draw function), 3.2.5, 3.2.7
- 4.1.C4, 4.1.C7, 4.2.2

### Predicting survival on the Titanic
In this exercise you will be working on creating a model for predicting whether a passenger on [RMS Titanic](https://en.wikipedia.org/wiki/RMS_Titanic) would survive the well-known fate of the ship. The case is taken from [Kaggle](http://kaggle.com), a website hosting machine learning competitions. The Titanic competition is known for being an entry level Kaggle competition and its wide use as an introduction to machine learning.

The exercise is two-fold:
- Part 1: This week you will explore and prepare the data
- Part 2: Next week you will use scikit-learn to train a model 

The case is called [Titanic: Machine Learning from Disaster](https://www.kaggle.com/c/titanic) on Kaggle (you may need to sign up, but it is free!). If you sign up, you will also have access to other notebooks. You should not hesitate exploring these and learn from others.

You should use **Jupyter** to solve the exercise!

#### Part 1
- Download the [training data](https://raw.githubusercontent.com/patrickcording/02807-comp-tools/master/docker/work/data/titanic.csv) 

- Read the case description on Kaggle and look at the data. Make sure you understand the features of the data.

- Explore the data. You can ask yourself questions like: which features are more likely to influence a passengers chance of survival? How will you investigate this?  

- Prepare the data for modelling. You should consider the following:
    + Do features have the correct data types?
    + How will you handle missing values?
    + Are there features you should not include?
    + Is cleaning needed for any of the features?
    + Can you think of any other feature engineering that might have an impact? (hint: cabin number)

