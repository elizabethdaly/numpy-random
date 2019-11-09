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
    1. [The normal distribution](#Eg1_sec3)
    2. [The binomial distribution](#Eg2_sec3)
    3. [The exponential distribution](#Eg3_sec3)
    4. [The Rayleigh distribution](#Eg4_sec3)
    5. [The logistic distribution](#Eg5_sec3)
    
5. [The use of seeds in generating pseudorandom numbers](#section4)
    
6. [Conclusion](#conclusion)

7. [References](#references)

## 1. Introduction <a name="introduction"></a>
- This README describes work done on the numpy.random package for the Programming for Data Analysis module assessment, due 11 November 2019. Resources used include Python and associated packages Jupyter, matplotlib, and NumPy. 
- The analysis takes the form of a single Jupyter notebook of filename given above. To view this file, download it from this repository and start Jupyter notebook from the folder containing the file. Jupyter notebook comes as part of the Anaconda distribution of Python (as do the other packages listed above). 
- Alternatively, view a static version of the notebook (by providing its GitHub url) using Jupyter Nbviewer.
- All images intended for inclusion in this README are located in the **images** subdirectory of this repository.
- I have tried to structure the Jupyter notebook and this README so that they have corresponding sections. However, I do not wish to merely repeat here what has been stated in the notebook. I will endevour to have this README summarize the work of the notebook and, hopefully, complement the analyses done there.

<p align="center"> 
    <img src=images/Planche_de_Galton.jpg width="400" height="300">
 </p>
 
 https://commons.wikimedia.org/w/index.php?curid=4213838 *Image credit: Antoine Taveneaux - Own work, CC BY-SA 3.0* This is an example of a bean machine, a device invented by Sir Francis Galton (in the days before numpy.random) to demonstrate that, for large sample sizes, the binomial distribution approximates a normal distribution.  
<!--
![BeanMachine](images/Planche_de_Galton.jpg)
By Antoine Taveneaux - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=4213838
-->


## 2. The purpose of the numpy.random package  <a name="section1"></a>
<!--The Python NumPy package (Numerical Python) is widely used for numerical computing in Python. At its core is ndarry, a multidimensional array which allows for fast mathematical operations on arrays without the need to write loops. This is called vectorization *i.e.* operations on arrays of appropriate size are carried out element-wise. NumPy makes working with large arrays of data efficient.-->

There is a Python module called *random* which can be used to generate pseudorandom numbers, so why the need for numpy.random? When researching the difference between *random* and *numpy.random* I found some useful stackoverflow posts. It seems that Python's built-in random module generates single numbers, while numpy.random can easily generate large arrays  (or just single numbers) containing sample values from lots of different kinds of probability distribution. It is based on the NumPy ndarray, which allows for fast mathematical operations on arrays without the need to write loops. Arrays are essential for representing matrices, which are in turn very important in modelling real world scenarios. For example, in the past, I have performed the calculations for control systems and done image processing using matrix algebra. numpy.random also contains functions to perform random shuffling of the contents of arrays and others which provide some information on, and control of, the seed used to generate the random numbers.  

In probability theory and statistics, the **probability distribution** of a variable describes the probability of occurance of each possible value of the variable over a number of trials. The mathematical function describing the probability that a particular value will occur is called the **probability density function** or **PDF**. It describes the likliehood of obtaining the possible values that the random variable can take on. 

For example, imagine an experiment to measure the temperature in Galway every day over the summer. We know that the values will fall within a fairly consistent range, and the most commonly measured value will be the average or mean. The variable (temperature) can theoretically take on any value in a continuous range of values, but certain values are more likely to occur than others, so there will be some spread in the measured values around the mean. At the end of the summer a histogram of temperature values would result in a bell-shaped curve. This experiment could be simulated with a probability distribution of a continuous variable such as the normal distribution. 

There are other experiemnts where the output is discrete rather than continuous. The simplest example of such an experiment is to imagine flipping a coin a number of times and attempting to predict how often each of the possible outcomes, heads (H) or tails (T), will occur. Here, the possible outcomes are discrete (H or T) and each is as likely to occur as the other with a fair coin. The coin toss experiment could be simulated using a discrete PDF such as the binomial distribution. The numpy.random package provides the ability to simulate any random process as it can be used to generate sample values from many types of probability distribution.

The **cumulative probability distribution (CDF)** of a random variable X, with a given PDF, is the probability that X will have values less than or equal to x. The CDF is obtained by integrating the PDF up to x; it is the area under the PDF curve up to x. So, if we know the distribution of some random variable X, we can make predictions about the probabitily that X will lie inside a specified range using its CDF. I demonstrate this in the notebook for some of the distributions. 
<!--pics of pdf and cdf maybe -->

## 3. Simple random data and Permutations <a name="section2"></a>

### 3 i Simple random data functions <a name="sec2SRD"></a>
The simple random data functions in the numpy.random package allow for the generation of arrays of random numbers of different types (floats, integers), within specified ranges, or from a provided array. The easiest way to explain the range of functionality provided is to illustrate with a few functions. Some functions on the documentation page appear to have identical explanations, but it turns out that some are deprecated (allowed but discouraged) and others are aliases to a single function.  

### 3 ii Permutations functions <a name="sec2PER"></a>
The permutations functions provide for random shuffling of data. 

## 4. Examples of distributions functions <a name="section3"></a>
I will discuss five probability distributions here and illustrate their use in the Jupyter notebook. 

### 4 i The normal distribution <a name="#Eg1_sec3"></a>
This function is used to generate random samples from a normal (Gaussian) distribution. It is a symmetric probability density function with a characteristic bell shaped curve. It is characterised primarily by its mean and variance.
The normal distributions occurs often in nature. The numpy.random documentation states that it describes the distribution of samples influenced by a large number of tiny, random disturbances, each with its own unique distribution. Uses include:
- IQ scores in a population are normally distibuted.
- In biology the log of variables tend to be normally distributed, for example heights, weights, blood pressure of adult humans, lengths of hair, nails, and teeth.
- errors in physical experiments can be simulated with the normal distribution.
- bell-curve grading can assign grades assuming a normal distribution.

### 4 ii The binomial distribution <a name="#Eg2_sec3"></a>
A binomial distribution can be thought of as simply the probability of a success or failure outcome in an experiment that is repeated multiple times. The binomial is a type of distribution that has two possible outcomes (the prefix “bi” means two, or twice), so the random variable is discrete. This distribution can be used to model a fixed number of trials n, each with a constant probability of success p. Our example above of flipping a fair coin (50% chance of getting a head) n times can be simulated using a binomial distribution. It can be used to simulate any experiment where the possible outcomes are success or failure such as:
1. The chance of obtaining a certain number of heads on flipping a coin a number of times.
2. The chance of winning (or not) a lottery.
3. The success or failure of a drug in a clinical trial.
4. The chances of finding oil (or not) when digging a well (exampe in numpy.random documentation).
5. The probability that a call centre employee will make a sale.  

The Poisson distribution (also available in numpy.random) is a special case of the binomial when the number of trials becomes very large and the probability of success in each one is very small.

### 4 iii The exponential distribution <a name="#Eg3_sec3"></a>
The exponential distribution is a continuous probability distribution used to model the time we must wait before some given event occurs. One interesting thing I learned is that exponential distributions are the only continuous distributions that are memoryless. This means that the probability distribution is independent of its history: any time may be marked down as time zero, so the likelihood of something happening in the future has no relation to whether or not it has happened in the past. This is also true of coin flips, but they follow the discrete binomial distribution. The lumen website in the references below has lots of examples of real world situations which can be simulated with the exponential distribution. These include:
- The amount of time until an earthquake occurs, beginning now.
- The amount of time, in months, a car battery lasts.
- The value of change in your pocket over time.
- The time between page requests on Wikipedia (example in numpy.random documentation)
- The size of raindrops (which grow with time) in rainstorms (example in numpy.random documentation)
- The number of days ahead of travel that people purchase flights.
- Failure of computer parts over time.

### 4 iv The Rayleigh distribution <a name="#Eg4_sec3"></a>
The Rayleigh distribution is a non-symmetric continuous probability distribution for positive random variables. It is mamed after Lord Rayleigh, a British physicist who provided the first theoretical explanation for why the sky is blue, among other things. A Rayleigh distribution is often observed when the magnitude of a vector is related to its directional components. For example, when wind speed is analyzed in two directions (say east and west components), the overall wind speed will follow a Rayleigh distribution. Each component must be normally distributed, with zero mean and equal variances, and there must be no linear relationship between the two constituent components. Knowledge of the wind speed distribution is very important when selecting sites for wind turbines for example. The mean and variance of this distribution are calculated from its scale (see the Jupyter notebook).
The Rayleigh distribution can be used: 
- to model the wind distribution for land-based wind turbine sites (the most common real-world application I found).
- to account for the distribution of background noise in magnetic resonance images magnitude images.
- to describe the distribution of wave heights under certain conditions (Science Direct reference).
- in communications to model the paths taken by a signal traveling through a dense scatterer towards a receiver.  

It is a special case of the Weibul distribution, which is also available with numpy.random.

### 4 v The logistic distribution <a name="#Eg5_sec3"></a>
The logistic distribution is a symmetric continuous probability distribution. It is very similar to the normal distribution but with higher tails (so that it falls away to zero a little more slowly). For this reason it is useful for predicting the likliehood of extreme events and for taking into account the underlying or base data. It is also used because its CDF (the logistic function) has a simple formula which approximates the normal distribution very well. It has applications in:
- the modeling of population growth, 
- logistic regression for classification purposes,
- world chess rankings where the performance of each player is a logistically distributed random variable,
- medicine to model the growth of tumours.

## 5. The use of seeds in generating pseudorandom numbers <a name="section4"></a>
The Real Python reference below asks the question: How random is random? Pseudorandom numbers (as opposed to truly random ones) are generated in the computer via algorithms called pseudorandom number generators. However, the behviour of a generator can be predicted if the seed used to initialize it is known. Obviously, that's not a good situation for security-sensitive applications such as cryptography. So it's important to know a little bit about how these numbers are generated in the computer. 

Python uses the Mersenne Twister as the core generator. It was developed in 1997 and is now the most widely-used pseudorandom number generator. The period length of the generator is chosen to be a Mersenne Prime, hence its name. A Mersenne prime is a prime number that is one less than a power of two; it has the form 2<sup>n</sup>-1 where n is an integer. The algorithm itself generates numbers in the range [0, 2<sup>w</sup>-1] where w is the word size in bits. The state of the pseudorandom number generator must be initialized or seeded by providing a w-bit seed value. The last group of functions in the numpy.random package is concerned with this seed. The Jupyter notebook associated with this README contains some examples of their use.

As both Python *random* and *numpy.random* are completely deterministic if some information about the seed of the generator is known, neither are suitable for security or cryptographic applications. There is a module called *secrets* which seems to be recommended for those types of application.

## 6. Conclusions <a name="conclusion"></a>
Machine learning mastery...

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
- [6] NumPy
https://numpy.org/
- [7] GitHub
https://github.com/
- [8] Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython. 
Wes McKinney. ISBN-13: 978-1491957660 ISBN-10: 1491957662
- [9] Random sampling (numpy.random)
https://docs.scipy.org/doc/numpy-1.16.0/reference/routines.random.html

**Related to random number generation in Python:**

- [10] Python random module
https://docs.python.org/3/library/random.html
- [11] Python Random Number Generation tutorial
https://pynative.com/python-random-module/
- [12] Generating Random Data in Python (Guide)
https://realpython.com/python-random/
- [13] Real Python: Generating Random Data in Python (Guide)
https://realpython.com/python-random/
- [14] Differences between numpy.random and random.random in Python
https://stackoverflow.com/questions/7029993/differences-between-numpy-random-and-random-random-in-python
- [15] Performance difference between numpy.random and random.random in Python
https://stackoverflow.com/questions/57220804/performance-difference-between-numpy-random-and-random-random-in-python
- [16] Machine Learning Mastery: How to Generate Random Numbers in Python
https://machinelearningmastery.com/how-to-generate-random-numbers-in-python/

**Statistics:**

- [17] STAT TREK Teach yourself statistics
https://stattrek.com/
- [18] What is a probability distribution? 
https://en.wikipedia.org/wiki/Probability_distribution
- [19] Difference between various numpy random functions
https://stackoverflow.com/questions/18829185/difference-between-various-numpy-random-functions
- [20] shuffle vs permute numpy
https://stackoverflow.com/questions/15474159/shuffle-vs-permute-numpy
- [21] What is the relationship betweeen a pdf and cdf?
https://math.stackexchange.com/questions/1302015/what-is-the-relationship-betweeen-a-pdf-and-cdf/1302451

**Normal distribution:**

- [22] Stat Trek The Normal Distribution
https://stattrek.com/probability-distributions/normal.aspx
- [23] WIKIPEDIA Normal distribution
https://en.wikipedia.org/wiki/Normal_distribution
- [24] Wolfram MathWorld: Normal Distribution
http://mathworld.wolfram.com/NormalDistribution.html

**Binomial distribution:**

- [25] WIKIPEDIA: Binomial distribution
https://en.wikipedia.org/wiki/Binomial_distribution
- [26] Binomial Distribution: Formula, What it is and How to use it
https://www.statisticshowto.datasciencecentral.com/probability-and-statistics/binomial-theorem/binomial-distribution-formula/
- [27] Fun with the Binomial Distribution
https://towardsdatascience.com/fun-with-the-binomial-distribution-96a5ecabf65b
- [28] Deriving the Poisson Distribution from the Binomial Distribution
https://medium.com/@andrew.chamberlain/deriving-the-poisson-distribution-from-the-binomial-distribution-840cc1668239
- [29] Poisson distribution
https://www.statisticshowto.datasciencecentral.com/poisson-distribution/

**Exponential distribution:**

- [30] WIKIPEDIA: Exponential distribution
https://en.wikipedia.org/wiki/Exponential_distribution
- [31] Wolfram MathWorld: Exponential Distribution
http://mathworld.wolfram.com/ExponentialDistribution.html
- [32] StatLect: Exponential Distribution
https://www.statlect.com/probability-distributions/exponential-distribution
- [33] lumen: The Exponential Distribution
https://courses.lumenlearning.com/introstats1/chapter/the-exponential-distribution/
- [34] Staistics How To: Memoryless Property
https://www.statisticshowto.datasciencecentral.com/memoryless-property/

**Rayleigh distribution:**

- [35] WIKIPEDIA: Rayleigh distribution
https://en.wikipedia.org/wiki/Rayleigh_distribution
- [36] ScienceDirect: Rayleigh Distribution
https://www.sciencedirect.com/topics/engineering/rayleigh-distribution
- [37] Brighton Webs Ltd.: Rayleigh Distribution
https://web.archive.org/web/20090514091424/http://brighton-webs.co.uk:80/distributions/rayleigh.asp
- [38] MathWorks: Rayleigh distribution
https://uk.mathworks.com/help/stats/rayleigh-distribution.html
- [39] Staistics How To: Rayleigh distribution
https://www.statisticshowto.datasciencecentral.com/rayleigh-distribution/

**Logistic distribution:**

- [40] Staistics How To: Logistic Distribution
https://www.statisticshowto.datasciencecentral.com/logistic-distribution/
- [41] WIKIPEDIA: Logistic distribution
https://en.wikipedia.org/wiki/Logistic_distribution
- [42] ScienceDirect: Logistic distribution
https://www.sciencedirect.com/topics/mathematics/logistic-distribution
- [43] WIKIPEDIA: Logistic function
https://en.wikipedia.org/wiki/Logistic_function

**Random number generators:**

- [44] WIKIPEDIA: Mersenne Twister
https://en.wikipedia.org/wiki/Mersenne_Twister
- [45] stackoverflow: How to use random.RandomState
https://stackoverflow.com/questions/32462273/how-to-use-random-randomstate
