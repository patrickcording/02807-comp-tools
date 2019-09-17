# Week 3
## Reading
- [HTTP protocol](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)
- [Application Programming Interface](https://en.wikipedia.org/wiki/Application_programming_interface)
- [REST](https://en.wikipedia.org/wiki/Representational_state_transfer)
- [Requests - http for humans - Quickstart](https://2.python-requests.org/en/master/user/quickstart/)
- [Supervised learning with scikit-learn](https://scikit-learn.org/stable/supervised_learning.html) (this is the full documentation)

## Exercises
### Exercise 1: Getting data from an API
In this exercise you should graph the exchange rates over time for one or more currencies of your choice versus, for example, the dollar.

- Use the [foreign exchange rates API](https://exchangeratesapi.io) to get exchange rates for a period.
- Load the data into Pandas and prepare it for plotting.
- Use matplotlib to show the exchange rate over time.

### Exercise 2: Searching Flickr
In this exercise you should write a function that uses the [Flickr Public Feed API](https://www.flickr.com/services/feeds/docs/photos_public/) to find and display photos. This API allows you to search for photos by author and tags.

- Write a function that takes a tag as input, sends a request to the API, and prints the response in JSON format. Familiarize yourself with the structure of the response.
- Extend your function to display the resulting images in your notebook. _Hint: to display images you can use the display library in IPython as follows._
```python
from IPython.display import Image
from IPython.display import display
urls = ['url1', 'url2']
images = map(lambda x: Image(x), urls)
display(*images)
```
- Extend your function to order the results by date so that the newest photo is shown first.
- Extend your function to also take a title keyword as input and filter the search results according to whether the keyword is in the title.

### Exercise 3: Predicting survival on the Titanic (training a model)
In this exercise you should use scikit-learn to train a model you can use for predicting survival on the Titanic.

If you didn't finish the data exploration and preparation last week, then continue with this now.

For inspiration, you may look at how [others](https://www.kaggle.com/c/titanic/notebooks) have done this. [This](https://www.kaggle.com/nadintamer/titanic-survival-predictions-beginner) is a very clean, beginner-friendly notebook. [This](https://towardsdatascience.com/predicting-the-survival-of-titanic-passengers-30870ccc7e8) blog post may also serve as inspiration.

#### Training a model
You should use scikit-learn to train a model. Pick at least 5 models, train them with the data you prepared, and compare the results. For example, the following models are available in scikit-learn.

- Random Forest
- Decision Tree
- K Nearest Neighbor
- Logistic Regression
- Linear Support Vector Machine

You should use scikit-learn to compare the models that you have trained. You should also pick a model and use scikit-learn to extract the importance of the features in your data to the model. 

#### What's next?
Once you have built a model you can use it to make predictions. To see your model in action you can download the unlabeled test data from Kaggle (see the [Titanic case](https://www.kaggle.com/c/titanic/) on Kaggle) and make predictions on that.

If you want to know how well you did, you can create a Kaggle account and submit the predictions you made on the test data and put your name on the leaderboard.

## More fun with APIs
There is a vast number of APIs for you to explore. [This list](https://github.com/public-apis/public-apis) is a good starting point if you are looking for inspiration. It has not been update for a while, but many of the links are still valid.

In Denmark, a lot of data has been made publicly available. For example, [Danmarks Adressers Web API](https://dawa.aws.dk/) lets you search and retrieve information about all addresses in Denmark. Unfortunately, both documentation and the actual API responses are in danish. Danmarks Statistik is also [exposing their data through a public API](https://www.dst.dk/da/Statistik/statistikbanken/api).

