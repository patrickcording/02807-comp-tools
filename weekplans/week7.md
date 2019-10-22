# Week 7
## Reading
- [Mining of Massive Datasets, Chapter 4](http://infolab.stanford.edu/~ullman/mmds/ch4.pdf) (Section 4.1).
- [Boyer–Moore majority vote algorithm](https://en.wikipedia.org/wiki/Boyer%E2%80%93Moore_majority_vote_algorithm).
- [Scalable Simple Random Sampling and Stratified Sampling](http://proceedings.mlr.press/v28/meng13a.pdf) (Section 1 and 2), X. Meng.

## Exercises
### Exercise 1: Reservoir sampling
Implement reservoir sampling in Python.

You may assume that a Python list or generator is your stream. Just make sure that your algorithm does not make more than one pass over the list and that it is not using random access to the list.

### Exercise 2: Finding the majority element in a file
In this exercise you should find the majority element in a remote file. The file contains one element per line, and the elements are 8-character strings. You should assume that the file is too big to download and store on your local disk.

The file is `https://02807-comp-tools.s3.us-east-2.amazonaws.com/majority`.

You can read a remote file line-by-line using the following snippet.

```python
import urllib
with urllib.request.urlopen('https://02807-comp-tools.s3.us-east-2.amazonaws.com/majority') as f:
    for line in f:
        element = str(line.rstrip())
        # Do something with the element
```

- Implement the majority algorithm and run it for the file to determine if there is a majority element. Tip: When developing the algorithm and you want to test it, you can limit the number of lines that you read from the file, so that you don't need to wait for reaching the end of the stream for each test.

In the lecture you were told that if the algorithm returns element `e`, it either holds that `e` is the majority element or there isn't a majority element.

- Modify your algorithm so that it always returns the majority element or `None`. Hint: A file stream may be read multiple times.

### Exercise 3: Stratified sampling
[Stratified sampling](https://en.wikipedia.org/wiki/Stratified_sampling) is a useful method for ensuring a representative ratio between subpopulations when doing random sampling. A random sample may not be representative of the population. 

For example, suppose you want to conduct a study to find the answer to the question "Are men or women better drivers?" in the general public. Due to limited time and resources you can only survey students on the campus of DTU. 
You draw a sample using simple random sampling and conclude that approximately 65% of the population thinks that men are better drivers. 

What went wrong? The ratio between men and women at DTU does not reflect the general population (see eg. [this editorial](https://www.dtu.dk/english/About/ORGANIZATION/OFFICE-of-the-PRESIDENT/Editorials/June-2018)). 

In this exercise you should use reservoir sampling to do stratified sampling on a stream. You may extend the implementation of reservoir sampling from exercise 1.

You may use the following generator function to generate data. It generates a stream of survey answers where about 65% of the answers are from males and most of the participants say that their own gender are the better drivers.

```python
import random
def survey_answers():
    while True:
        gender = 1 if random.random() < 0.65 else 0
        answer = gender if random.random() < 0.98 else abs(gender-1)
        yield {
            'gender': gender,
            'answer': answer
        }
```

### Exercise 4: Composing reservoirs
Imagine that you have been sampling from two streams using reservoir sampling, and now have two reservoirs of size ![equation](https://latex.codecogs.com/gif.latex?k). You have seen ![equation](https://latex.codecogs.com/gif.latex?n_1) elements from the first stream and ![equation](https://latex.codecogs.com/gif.latex?n_2) elements from the second stream. Describe a way to combine the two reservoirs to obtain a sample of size ![equation](https://latex.codecogs.com/gif.latex?k), where every element was sampled with probability ![equation](https://latex.codecogs.com/gif.latex?k/(n_1+n_2)).

### Exercise 5: Extending the majority algorithm
The majority algorithm reports if an element occurs more than half of the time, but sometimes you want "majority" to mean more than ![equation](https://latex.codecogs.com/gif.latex?1/x) times (for ![equation](https://latex.codecogs.com/gif.latex?x>2)).

- Modify the majority algorithm to be able to find if an element occurs more than ![equation](https://latex.codecogs.com/gif.latex?1/x) times. You can start by finding an algorithm for ![equation](https://latex.codecogs.com/gif.latex?x=3) and then try to generalize it afterwards. You don't have to implement your solution, just describe the algorithm.

- Suppose you know that the number of distinct elements in the stream is ![equation](https://latex.codecogs.com/gif.latex?D). What happens to the space usage of your algorithm if you set ![equation](https://latex.codecogs.com/gif.latex?x=D)?

### Exercise 6: Another proof for reservoir sampling
In the lecture we saw that the probability of element number ![equation](https://latex.codecogs.com/gif.latex?i) being in the reservoir at the end of a stream of length ![equation](https://latex.codecogs.com/gif.latex?m) is

![equation](https://latex.codecogs.com/gif.latex?P[\text{i%20is%20in%20S}]%20=%20\frac%20k%20i%20\cdot%20\prod_{j=i+1}^m%20(\frac%20k%20j%20\cdot%20\frac{k-1}{k}+%20(1-\frac%20k%20j))%20=%20\frac%20k%20m)

The fact that the probability is ![equation](https://latex.codecogs.com/gif.latex?k/m) for all ![equation](https://latex.codecogs.com/gif.latex?i) can also be proved by induction. This proof avoids having to simplify a product sequence (which is tedious to type into a calculator, and even more so to solve by hand).

Prove that the probability of selecting an element for a sample of size ![equation](https://latex.codecogs.com/gif.latex?k) in a stream of size ![equation](https://latex.codecogs.com/gif.latex?m) is ![equation](https://latex.codecogs.com/gif.latex?k/m).

Hint: For the base case, you should assume that ![equation](https://latex.codecogs.com/gif.latex?k=m=1).

