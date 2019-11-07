# The Python numpy.random package
## Elizabeth Daly

### HDip Data Analytics 2019 Programming for Data Analysis Assessment

Git-hub repository at:
https://github.com/elizabethdaly/numpy-random.git

- Jupyter notebook: **numpy-random.ipynb**

![NumPy](images/numpy_logo.png)

# Table of contents
1. [Introduction](#introduction)

2. [The purpose of the numpy.random package](#section1)

3. [Simple random data and Permutations](section2)
    1. [Simple random data functions](#sec2SRD)
    2. [Permutations functions](#sec2PER)
    
4. [Examples of distributions functions](#section3)
    1. [Example 1](#Eg1_sec3)
    2. [Example 2](#Eg2_sec3)
    3. [Example 3](#Eg3_sec3)
    4. [Example 4](#Eg4_sec3)
    5. [Example 5](#Eg5_sec3)
    
5. [The use of seeds in generating pseudorandom numbers](#section4)
    
6. [Conclusion](#conclusion)

7. [References](#references)

## 1. Introduction <a name="introduction"></a>
- This README describes work done on the numpy.random package for the Programming for Data Analysis module assessment, due 11 November 2019. Resources used include Python and associated packages Jupyter, matplotlib, and NumPy. 
- The analysis takes the form of a single Jupyter notebook of filename given above. To view this file, download it from this repository and start Jupyter notebook from the folder containing the file. Jupyter notebook comes as part of the Anaconda distribution of Python (as do the other packages listed above). 
- Alternatively, view a static version of the notebook (by providing its GitHub url) using Jupyter Nbviewer.
- All images intended for inclusion in this README are located in the **images** subdirectory of this repository.
- I have tried to structure the Jupyter notebook and this README so that they have corresponding sections. However, I do not wish to merely repeat here what has been stated in the notebook. I will endevour to have this README summarize the work of the notebook and, hopefully, complement the analyses done there.

## 2. The purpose of the numpy.random package  <a name="section1"></a>
<!--The Python NumPy package (Numerical Python) is widely used for numerical computing in Python. At its core is ndarry, a multidimensional array which allows for fast mathematical operations on arrays without the need to write loops. This is called vectorization *i.e.* operations on arrays of appropriate size are carried out element-wise. NumPy makes working with large arrays of data efficient.-->

There is a Python module called *random* which can be used to generate pseudorandom numbers, so why the need for numpy.random? When researching the difference between *random* and *numpy.random* I found some useful stackoverflow posts. It seems that Python's built-in random module generates single numbers, while numpy.random can easily generate large arrays  (or just single numbers) containing sample values from lots of different kinds of probability distribution. It is based on the NumPy ndarray, which we have already mentioned. Arrays are essential for representing matrices, which are in turn very important in modelling real world scenarios. For example, in the past, I have performed the calculations for control systems and done image processing using matrix algebra. numpy.random also contains functions to perform random shuffling of the contents of arrays and others which provide some information on, and control of, the seed used to generate the random numbers.  

In probability theory and statistics, the **probability distribution** of a variable describes the probability of occurance of each possible value of the variable over a number of trials. The mathematical function describing the probability that a particular value will occur is called the **probability density function** or **PDF**. It describes the likliehood of obtaining the possible values that the random variable can take on. 

For example, imagine an experiment to measure the temperature in Galway every day over the summer. We know that the values will fall within a fairly consistent range, and the most commonly measured value will be the average or mean. The variable (temperature) can theoretically take on any value in a continuous range of values, but certain values are more likely to occur than others, so there will be some spread in the measured values around the mean. At the end of the summer a histogram of temperature values would result in a bell-shaped curve. This experiment could be simulated with a probability distribution of a continuous variable such as the normal distribution. 

There are other experiemnts where the output is discrete rather than continuous. The simplest example of such an experiment is to imagine flipping a coin a number of times and attempting to predict how often each of the possible outcomes, heads (H) or tails (T), will occur. Here, the possible outcomes are discrete (H or T) and each is as likely to occur as the other with a fair coin. The coin toss experiment could be simulated using a discrete PDF such as the binomial distribution. The numpy.random package provides the ability to simulate any random process as it can be used to generate sample values from many types of probability distribution.

The **cumulative probability distribution (CDF)** of a random variable X, with a given PDF, is the probability that X will have values less than or equal to x. The CDF is obtained by integrating the PDF up to x; it is the area under the PDF curve up to x. So, if we know the distribution of some random variable X, we can make predictions about the probabitily that X will lie inside a specified range using the CDF. 
<!--pics of pdf and cdf maybe -->

## 3. Simple random data and Permutations <a name="section2"></a>

### 3 (i) Simple random data functions <a name="sec2SRD"></a>
The simple random data functions in the numpy.random package allow for the generation of arrays of random numbers of different types (floats, integers), within specified ranges, or from a provided array. The easiest way to explain the range of functionality provided is to illustrate with a few functions. Some functions on the documentation page appear to have identical explanations, but it turns out that some are deprecated (allowed but discouraged) and others are aliases to a single function.  

### 3 (ii) Permutations functions <a name="sec2PER"></a>
The permutations functions provide for random shuffling of data. 

## 4. Examples of distributions functions <a name="section3"></a>
Intro.
For each can calculate mean, variance, cdf etc moments.
<!-- ones with easy to find and explain apps-->

### 4 (i) normal <a name="#Eg1_sec3"></a>
This function is used to generate random samples from a normal (Gaussian) distribution. It has a probability density function with a characteristic bell shaped curve. Refs. 

The normal distributions occurs often in nature. 
1. real world one
2. real world two

### 4 (ii) binomial <a name="#Eg2_sec3"></a>
A binomial distribution can be thought of as simply the probability of a success or failure outcome in an experiment that is repeated multiple times. The binomial is a type of distribution that has two possible outcomes (the prefix “bi” means two, or twice), so the random variable is discrete. This distribution can be used to model a fixed number of trials n, each with a constant probability of success p. Our example above of flipping a fair coin (50% chance of getting a head) n times can be simulated using a binomial distribution. It can be used to simulate any experiment where the possible outcomes are success or failure such as:
1. The chance of obtaining a certain number of heads on flipping a coin a number of times.
2. The chance of winning (or not) a lottery.
3. The success or failure of a drug in a clinical trial.
4. The chances of finding oil (or not) when digging a well (in numpy.random documentation).
5. The probability of a call centre employee of making a sale.  

The Poisson distribution is a special case of the binomial when the number of trials becomes very large and the probability of success in each one is very small.

### 4 (iii) exponential <a name="#Eg3_sec3"></a>
The exponential distribution is a continuous probability distribution used to model the time we must wait before some given event occurs. One interesting thing I learned is that exponential distributions are the only continuous distributions that are memoryless. This means that means that the probability distribution is independent of its history. Any time may be marked down as time zero, so the likelihood of something happening in the future has no relation to whether or not it has happened in the past. This is also true of coin flips, but they follow the discrete binomial distribution. The lumen website in the references below also has lots of examples of real world situations which can be simulated with the exponential distribution. These include:
- The amount of time until an earthquake occurs, beginning now.
- The amount of time, in months, a car battery lasts.
- The value of change in your pocket over time.
- The time between page requests on Wikipedia (in numpy.random documentation)
- The size of raindrops (which grow with time) in rainstorms (in numpy.random documentation)
- The number of days ahead of travel that people purchase flights.
- Failure of computer parts over time.

### 4 (iv) rayleigh <a name="#Eg4_sec3"></a>
Continuous. Named after Lord Rayleigh. Wave heights. Wind speed - turbines.

### 4 (v) Example 5 <a name="#Eg5_sec3"></a>

## 5. The use of seeds in generating pseudorandom numbers <a name="section4"></a>
The Real Python reference below asks the question: How random is random? Pseudorandom numbers (as opposed to truly *random* ones) are generated in the computer via algorithms called pseudorandom number generators. However, the behviour of a generator can be predicted if the seed used to initialize it is known. Obviously, that's not a good situation for security-sensitive applications such as cryptography. So it's important to know a little bit about how these numbers are generated in the computer. 

Python uses the Mersenne Twister as the core generator. It was developed in 1997 and is now the most widely-used pseudorandom number generator. The period length of the generator is chosen to be a Mersenne Prime, hence its name. A Mersenne prime is a prime number that is one less than a power of two; it has the form 2<sup>n</sup>-1 where n is an integer. The algorithm itself generates numbers in the range [0, 2<sup>w</sup>-1] where w is the word size in bits. The state of the pseudorandom number generator must be initialized or seeded by providing a w-bit seed value. The last group of functions in the numpy.random package is concerned with this seed. The Jupyter notebook associated with this README contains some examples of their use.

As both Python *random* and *numpy.random* are completely deterministic if some information about the seed of the generator is known, neither are suitable for security or cryptographic applications. There is a module called *secrets* which seems to be recommended for those types of application.

## 6. Conclusions <a name="conclusion"></a>

## 7. References <a name="references"></a>

**General:**

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
- [10] NumPy
https://numpy.org/
- [6] GitHub
https://github.com/
- [15] Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython. 
Wes McKinney. ISBN-13: 978-1491957660 ISBN-10: 1491957662
- [11] Random sampling (numpy.random)
https://docs.scipy.org/doc/numpy-1.16.0/reference/routines.random.html

**Related to random number generation in Python:**

- [7] Python random module
https://docs.python.org/3/library/random.html
- [8] Python Random Number Generation tutorial
https://pynative.com/python-random-module/
- [9] Generating Random Data in Python (Guide)
https://realpython.com/python-random/
- [] Real Python: Generating Random Data in Python (Guide)
https://realpython.com/python-random/
- [12] Differences between numpy.random and random.random in Python
https://stackoverflow.com/questions/7029993/differences-between-numpy-random-and-random-random-in-python
- [] Performance difference between numpy.random and random.random in Python
https://stackoverflow.com/questions/57220804/performance-difference-between-numpy-random-and-random-random-in-python

**Statistics:**

- [13] STAT TREK Teach yourself statistics
https://stattrek.com/
- [14] What is a probability distribution? 
https://en.wikipedia.org/wiki/Probability_distribution
- [16] Difference between various numpy random functions
https://stackoverflow.com/questions/18829185/difference-between-various-numpy-random-functions
- [17] shuffle vs permute numpy
https://stackoverflow.com/questions/15474159/shuffle-vs-permute-numpy
- [] What is the relationship betweeen a pdf and cdf?
https://math.stackexchange.com/questions/1302015/what-is-the-relationship-betweeen-a-pdf-and-cdf/1302451

**Normal distribution:**

- [18] Stat Trek The Normal Distribution
https://stattrek.com/probability-distributions/normal.aspx
- [19] WIKIPEDIA Normal distribution
https://en.wikipedia.org/wiki/Normal_distribution
- [] Wolfram MathWorld: Normal Distribution
http://mathworld.wolfram.com/NormalDistribution.html

**Binomial distribution:**

- [20] WIKIPEDIA: Binomial distribution
https://en.wikipedia.org/wiki/Binomial_distribution
- [21] Binomial Distribution: Formula, What it is and How to use it
https://www.statisticshowto.datasciencecentral.com/probability-and-statistics/binomial-theorem/binomial-distribution-formula/
- [22] Fun with the Binomial Distribution
https://towardsdatascience.com/fun-with-the-binomial-distribution-96a5ecabf65b
- [] Deriving the Poisson Distribution from the Binomial Distribution
https://medium.com/@andrew.chamberlain/deriving-the-poisson-distribution-from-the-binomial-distribution-840cc1668239
- [23] Poisson distribution
https://www.statisticshowto.datasciencecentral.com/poisson-distribution/

**Exponential distribution:**

- [] WIKIPEDIA: Exponential distribution
https://en.wikipedia.org/wiki/Exponential_distribution
- [] Wolfram MathWorld: Exponential Distribution
http://mathworld.wolfram.com/ExponentialDistribution.html
- [] StatLect: Exponential Distribution
https://www.statlect.com/probability-distributions/exponential-distribution
- [] lumen: The Exponential Distribution
https://courses.lumenlearning.com/introstats1/chapter/the-exponential-distribution/
- [] Staistics How To: Memoryless Property
https://www.statisticshowto.datasciencecentral.com/memoryless-property/

**Rayleigh distribution:**

- [] WIKIPEDIA: Rayleigh distribution
https://en.wikipedia.org/wiki/Rayleigh_distribution
- [] ScienceDirect: Rayleigh Distribution
https://www.sciencedirect.com/topics/engineering/rayleigh-distribution

**Logistic distribution:**

- [] Staistics How To: Logistic Distribution
https://www.statisticshowto.datasciencecentral.com/logistic-distribution/

**Random number generators:**

- [] WIKIPEDIA: Mersenne Twister
https://en.wikipedia.org/wiki/Mersenne_Twister
- [] stackoverflow: How to use random.RandomState
https://stackoverflow.com/questions/32462273/how-to-use-random-randomstate
