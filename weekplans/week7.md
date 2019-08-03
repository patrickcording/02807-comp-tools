# Week 7
## Reading
- [Mining of Massive Datasets](http://www.mmds.org/#book), [chapter 4, section 4.1 and 4.2](http://infolab.stanford.edu/~ullman/mmds/ch4.pdf).
- [Scalable Simple Random Sampling and Stratified Sampling](http://proceedings.mlr.press/v28/meng13a.pdf), X. Meng, 2013.

## Exercises
### Exercise 1
Given the numbers 1 to 20, what is the probability of getting each of the following samples with Simple Random Sampling for _k_=5.

- 1,5,9,13,17
- 1,2,3,4,5
- 5,2,13,8,20
- 3,5,6,10,11,19

### Exercise 2: Reservoir sampling
- Implement reservoir sampling in Python.

For this exercise you may assume that a Python list is your stream. Just make sure that your algorithm does not make more than one pass over the list and that it is not using random access to the list.

- Imagine that you have been sampling from two streams, and now have two reservoirs of size _k_. Describe a way to combine these two to obtain a sample of size _k_. 

- Prove that the main property of simple random sampling is satisfied by reservoir sampling.

### Exercise 3: Stratified sampling
[Stratified sampling](https://en.wikipedia.org/wiki/Stratified_sampling) is a useful method for ensuring the ratio between subpopulations when doing random sampling.

Assume that the population you are sampling from is people, and there are 50% males and 50% females. Use the following snippet to generate a stream of people from the population.

```python
import random
stream = ['m' for _ in range(1,100)] + ['f' for _ in range(1,100)]
random.shuffle(stream)
stream
```

Solve the following exercises.

- What does the snippet do?
- Run your reservoir sampling algorithm from exercise 2 some times for the stream and count the number of males and females in the results. Is it consistent?
- Extend your algorithm to do stratified random sampling.

### Exercise 4: Distributed sampling
...

### Exercise 5
Solve exercise 4.2.1 from [the book](http://infolab.stanford.edu/~ullman/mmds/ch4.pdf).