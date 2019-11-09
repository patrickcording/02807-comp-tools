# Week 10
## Reading
- [Apache Spark - Under the Hood](https://pages.databricks.com/201805-EB-Mini-eBook-1-Under-The-Hood_landing.html) ([unofficial direct link](https://tanthiamhuat.files.wordpress.com/2019/01/apache-spark-under-the-hood.pdf)).
- [Spark SQL Guide - Getting Started](https://spark.apache.org/docs/2.4.4/sql-getting-started.html)

## Exercises
### Exercise 1: Your first Spark program
In this exercise you will use Spark to compute some simple aggregate statistics. To do this, we use the web traffic data from project 2 - you should already be familiar with this data.

First, download a [sample of the data](https://files.dtu.dk/fss/public/link/public/stream/read/traffic_2_sample?linkToken=oAqa4LkKmu2yCprl&itemName=traffic_2_sample). When your Spark programs are doing the right thing, you can try running them on the [full data](https://files.dtu.dk/fss/public/link/public/stream/read/traffic_2?linkToken=_DcyO-U3MjjuNzI-&itemName=traffic_2).

Solve the following exercises.

- Start a Spark session (see the notebook from the lecture)
- Load the data into a Spark dataframe. Remember that the delimiter is `\t` (the tab character)
- Create a Spark dataframe where the name the columns are `ip` and `domain` (use `select()` and `alias()`)
- Compute a Spark dataframe with the total number of IPs in the data and the number of distinct IPs in the data (use `count()` and `countDistinct()`)
- Compute a Spark dataframe with the total number of IPs and the number of distinct IPs per domain (use `groupBy()`)
- Create a dataframe ordered by the number of unique IPs in descending order (use `orderBy()` and `desc()`)
- Compute a Spark dataframe with the total number of IPs and the number of distinct IPs for the domains `databricks.com` and `dtu.dk` (use `filter()`)

### Exercise 2: Bracketing
In this exercise you should use Spark to count the number of Titanic passengers in different age brackets. I.e., you need to count the number of people age 0 to 9, 10 to 19, and so on.

- Load the Titanic data (`data/titanic.csv`) into a Spark dataframe (use schema inference)
- Remove the rows that do not have an age
- Create a new column with a value that identifies the bracket that passengers are in
- Compute a Spark dataframe with the sum of passengers in each bracket

### Exercise 3: Transformations vs Actions
For each of the following Spark operations, decide if they are transformations or actions.

- `select()`
- `groupBy()`
- `filter()`
- `where()`
- `count()`
- `show()`
- `agg()`
- `write()`

### Exercise 4: World Cities
For this exercise, you will need the [world cities data](https://simplemaps.com/static/data/world-cities/basic/simplemaps_worldcities_basicv1.5.zip) from [simplemaps.com](http://simplemaps.com). The dataset is described [here](https://simplemaps.com/data/world-cities).

- Load the data into a Spark dataframe. Make sure that columns have useful names. 
- Use Spark to find the city with the largest population size for each country.

- Write a Python function that computes the distance between two sets of latitude/longitude coordinates across the surface of the earth. It is sufficient that it produces an estimate of the distance, i.e., you can assume that the earth is a sphere with a perfectly even surface. 

In order to use your function on columns of a Spark DataFrame, you need to wrap it in a Spark user defined function (UDF).

- Define a UDF for wrapping your function. Hint: [this](https://docs.databricks.com/spark/latest/spark-sql/udf-python.html).

- Use Spark to find the nearest city to a given latitude/longitude coordinate.
- Use Spark to find the nearest city with a population above N.
- Use Spark to find the two cities in the world that are the furthest apart (Hint: Join you dataframe with itself).
- Use Spark to find the three cities A, B, and C in the same country, where the distance from A to B to C to A is the greatest.

### Exercise 5: Average vs Median
Sub-exercises marked with a **(*)** are particularly hard. Make sure you have solved the other exercises before you start working on this (and ask questions).

In this exercise you should compute averages and medians from the spending data you know from mandatory assignment 2.

- Use Spark to compute the average spending (use `avg()`)
- Use Spark to compute the median spending (there is no `median()`, instead you should use `approxQuantiles()`)

The function `approxQuantiles()` actually uses a sketch to approximate the median. There is no function that computes the exact median. 

- **(*)** Why is there no function that computes the exact median?

- Use Spark to compute the average spending per customer
- **(*)** Use Spark to compute the exact median of the spendings per customer. Make sure you have a strategy for how you want to this before you start coding.
