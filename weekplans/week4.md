# Week 4
## Reading
- [SQLite](https://www.sqlite.org/index.html)
- If you like reading a lot: [SQL Queries for Mere Mortals](https://www.google.com/search?ei=xpOEXeTCD4Kc_QbE5Y3oBg&q=sql+queries+for+mere+mortals+PDF&oq=sql+queries+for+mere+mortals+PDF&gs_l=psy-ab.3..0i71l8.0.0..4877...0.2..0.0.0.......0......gws-wiz.eUC5Vk5x3no&ved=0ahUKEwjkve--g9_kAhUCTt8KHcRyA20Q4dUDCAs&uact=5), John L. Viescas & Michael J. Hernandez
- If you want something more hands-on: [Introduction to SQL on W3Schools](https://www.w3schools.com/sql/sql_intro.asp)

## Exercises
You may solve todays exercises in Jupyter. [This notebook](https://github.com/patrickcording/02807-comp-tools/blob/master/docker/work/SQLite%20connection%20example.ipynb) shows how to use SQLite from Python.

### Exercise 1: Your first database
- Create a new database.
- Create a new table "measurements" in the database with the columns "sensor_id", "time", and "value" with types integer, integer, and real.
- Insert at least 5 rows of data into the table using SQL.
- Create a SELECT query to retrieve all the measurements.
- Create a SELECT query that returns the all the measurements from a given sensor_id.
- Use an UPDATE statement to change the value of one of the measurements.
- Use a DELETE statement to delete one of the measurements.

### Exercise 2: SQL challenges
In this exercise you will use the "measurements" table you created in the previous exercise.

- Create a query that returns all measurements where a given sensor_id has a value above a given threshold.
- Create a query that returns the total number of measurements and the average of all values.
- Create a query the returns the minimum, average and maximum value of measurements for each sensor_id.
- Add the possibility of specifying a time range for the above query.
- Make a query that returns all sensor_ids for which the maximum value has been over a given threshold.

Before you can solve the following challenges, you should create an extra table with the name sensors that has columns id of type integer, and name of type text. Insert names for the different sensor_id you have used in the measurements table.

- Create a query that returns all measurements for a sensor with a given name. Extend the query such that it is possible to specify a time range.
- Create a query that returns how many measurements each sensor have.

### Exercise 3: Indexing experiments
Solve the following exercises in Python.

- Insert rows in the measurements table such that it has a least 1.000.000 rows.
- Construct a SELECT query that returns all measurements for a given sensor_id in a given time period (i.e. where time is between a given start and end value). Ensure you query returns around 100 rows by picking appropriate
values for sensor_id, start and end.
- Measure how long time it takes to run the query (if it is too fast to measure, insert extra rows in the table). Hint: In Jupyter, you can write `%time` in the beginning of the cell, and it will output the execution time for the code in the cell.
- Create an index on the sensor_id column and see if it speeds up the query. You could also try to create an index on time, and the combination of sensor_id and time. Which one gives the best performance? Remember to delete the previous index before testing a new one (otherwise it is difficult to know which one is being used by the database).

### Exercise 4: Joins
Solve the exercises in [this notebook](https://github.com/patrickcording/02807-comp-tools/blob/master/docker/work/Week%204%20-%20Join%20exercises.ipynb).


