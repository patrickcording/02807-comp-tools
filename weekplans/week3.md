# Week 3
## Reading
- [HTTP protocol](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)
- [Application Programming Interface](https://en.wikipedia.org/wiki/Application_programming_interface)
- [REST](https://en.wikipedia.org/wiki/Representational_state_transfer)
- [Requests - http for humans - Quickstart](https://2.python-requests.org/en/master/user/quickstart/)
- [Scrapy tutorial](https://docs.scrapy.org/en/latest/intro/tutorial.html)
- [Supervised learning with scikit-learn](https://scikit-learn.org/stable/supervised_learning.html) (this is the full documentation)

## Exercises
### Exercise 1: Getting data from an API
In this exercise you should graph the exchange rates over time for one or more currencies of your choice versus for example the dollar.

- Use the [foreign exchange rates API](https://exchangeratesapi.io) to get exchange rates for a period.
- Load the data into Pandas and prepare it for plotting.
- Use matplotlib to show the exchange rate over time.

### Exercise 2: Creating a crawler

### Exercise 3: Predicting survival on the Titanic (EDA and data prep)
If you didn't finish the data exploration and preparation last week, then continue with this now.

_For inspiration, you may look at how [others](https://www.kaggle.com/c/titanic/notebooks) have done this. [This](https://www.kaggle.com/nadintamer/titanic-survival-predictions-beginner) is a very clean, beginner-friendly notebook._

### Exercise 4: Predicting survival on the Titanic (training a model)
Use scikit-learn to train a model for predicting survival on the Titanic.

The problem type is binary classification (did a passenger survice or die?). You should chose a number of different models for binary classification and compare their accuracy. To do so, be sure to split your data into training and validation and only feed the training data to your models.

Which model do you chose, and why?

_For inspiration, you may look at how [others](https://www.kaggle.com/c/titanic/notebooks) have done this. [This](https://www.kaggle.com/nadintamer/titanic-survival-predictions-beginner) is a very clean, beginner-friendly notebook._

### Exercise 5: Python brush-up
Continue solving the Python exercises from last week. 

## More fun with APIs
There is a vast number of APIs for you to explore. [This list](https://github.com/public-apis/public-apis) is a good starting point if you are looking for inspiration. It has not been update for a while, but many of the links are still valid.

In Denmark, a lot of data has been made publicly available. For example, [Danmarks Adressers Web API](https://dawa.aws.dk/) lets you search and retrieve information about all addresses in Denmark. Unfortunately, both documentation and the actual API responses are in danish. Danmarks Statistik is also [exposing their data through a public API](https://www.dst.dk/da/Statistik/statistikbanken/api).

