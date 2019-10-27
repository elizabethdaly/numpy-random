# The Python numpy.random package
## Elizabeth Daly

### HDip Data Analytics 2019 Programming for Data Analysis Assessment

Git-hub repository at:
https://github.com/elizabethdaly/numpy-random.git

- Jupyter notebook: numpy-random.ipynb

![NumPy](images/numpy_logo.png)

# Table of contents
1. [Introduction](#introduction)

2. [The purpose of the numpy.random package](#section1)

3. [Simple random data and Permutations](section2)
    1. [Simple random data functions](#sec2SRD)
    2. [Permutations functions](#sec2PER)
    
3. [Examples of distributions functions](#section3)
    1. [Example 1](#Eg1_sec3)
    2. [Example 2](#Eg2_sec3)
    3. [Example 3](#Eg3_sec3)
    4. [Example 4](#Eg4_sec3)
    5. [Example 5](#Eg5_sec3)
    
4. [The use of seeds in generating pseudorandom numbers](#section4)
    
5. [Conclusion](#conclusion)

6. [References](#references)

## Introduction <a name="introduction"></a>
This README describes work done on the numpy.random package for the Programming for Data Analysis module assessment, due 11 November 2019. Resources used include Python and associated packages Jupyter, matplotlib, and NumPy. The analysis takes the form of a single Jupyter notebook of filename given above. To view this file, download it from this repository and run Jupyter notebook, which comes as part of the Anaconda distribution of Python (as do the other packages listed above). Alternatively, view a static version of the notebook (by providing its GitHub url) using Jupyter Nbviewer. I have divided the work in the notebook into sections which roughly match this README.

## The purpose of the numpy.random package  <a name="section1"></a>
There is a Python module called *random* which can be used to generate pseudorandom numbers. When researching the difference between it and numpy.random I found some useful stackoverflow posts. It seems that ... explain. The numpy.random package is a group of functions to allow for efficient fast generation of large sample arrays (or just single numbers) containing sample values from lots of different kinds of probability distributions. It is based on the NumPy  ndarray, a structure  which is important for representing matrices, which are in turn very important in the real world. EG. ML maybe. NumPy itself is ...<!-- book-->
What is a distribution function? Why are they needed? Why so many different types?

To quote WIKIPEDIA: In probability theory and statistics, a **probability distribution** is a mathematical function that provides the probabilities of occurrence of different possible outcomes in an experiment. It describes the likliehood of obtaining the possible values that a random variable can take on. For example, imagine an experiment to measure the temperature in Galway every day over the summer. We know that the values will fall within a fairly consistent range, with some average value being the most common one. The variable (temperature) can theoretically take on any value, but certain values are more likely to occur than others and therefore there will be some spread in the measured values. At the end of the summer a histogram of temperature values would result in a bell-shaped curve. This experiment could be simulated with a probability distribution. There are other experiemnts where the output is discrete rather than continuous. The simplest example of such an experiment is to imagine flipping a coin a number of times and attempting to predict how often each of the possible outcomes, heads (H) or tails (T), will occur. Here, the possible outcomes are discrete (H or T) and each is as likely to occur as the other with a fair coin. The numpy.random package provides the ability to simulate any random process as it can be used to generate sample values from many types of probability distribution.

## Simple random data and Permutations <a name="section2"></a>

### Simple random data functions <a name="sec2SRD"></a>
The simple random data functions in the numpy.random package allow for the generation of arrays of random numbers of different types (floats, integers), within specified ranges, or from a provided array. The easiest way to explain the range of functionality provided is to illustrate with a few functions. Some functions on the documentation page appear to have identical explanations, but it turns out that some are deprecated (allowed but discouraged) and others are aliases to a single function. 

### Permutations functions <a name="sec2PER"></a>
The permutations functions provide for shuffling of data. 

## Examples of distributions functions <a name="section3"></a>
<!--real world examples of each?-->

### normal <a name="#Eg1_sec3"></a>
This function is used to generate random samples from a normal (Gaussian) distribution. It has a probability density function with a characteristic bell shaped curve. Refs. Explain pdf.

The normal distributions occurs often in nature. 
### Example 2 <a name="#Eg2_sec3"></a>
### Example 3 <a name="#Eg3_sec3"></a>
### Example 4 <a name="#Eg4_sec3"></a>
### Example 5 <a name="#Eg5_sec3"></a>

## The use of seeds in generating pseudorandom numbers <a name="section4"></a>
Pseudorandom numbers (as opposed to *random* numbers) are generated in the computer by algorithms, the behviour of which can be predicted depending on the seed of the random number generator. The numpy.random random number generation seed can be changed through use of numpy.random.seed.

## Conclusion <a name="conclusion"></a>

## References <a name="references"></a>

- [1]  Anaconda Distribution
https://www.anaconda.com/
- [2] Python Software Foundation
https://www.python.org/
- [3] Project Jupyter
https://jupyter.org/
- [4] Sharing Jupyter notebooks
https://nbviewer.jupyter.org/
- [5] matplotlib: Python plotting library
htts://matplotlib.org/
- [6] GitHub
https://github.com/
- [7] Python random module
https://docs.python.org/3/library/random.html
- [8] Python Random Number Generation tutorial
https://pynative.com/python-random-module/
- [] Generating Random Data in Python (Guide)
https://realpython.com/python-random/
- [9] NumPy
https://numpy.org/
- [10] Random sampling (numpy.random)
https://docs.scipy.org/doc/numpy-1.16.0/reference/routines.random.html
- [11] Differences between numpy.random and random.random in Python
https://stackoverflow.com/questions/7029993/differences-between-numpy-random-and-random-random-in-python
- [12] STAT TREK Teach yourself statistics
https://stattrek.com/
- [13] What is a probability distribution? 
https://en.wikipedia.org/wiki/Probability_distribution
- [14] Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython. 
Wes McKinney. ISBN-13: 978-1491957660 ISBN-10: 1491957662
- [15] Difference between various numpy random functions
https://stackoverflow.com/questions/18829185/difference-between-various-numpy-random-functions
- [16] shuffle vs permute numpy
https://stackoverflow.com/questions/15474159/shuffle-vs-permute-numpy
- [17] Stat Trek ref