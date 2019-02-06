---
layout: post
title:      "PAC LEARNING THEORY AND MACHINE LEARNING MADE SIMPLE…. I HOPE"
date:       2019-02-06 16:22:15 +0000
permalink:  pac_learning_theory_and_machine_learning_made_simple_i_hope
---


Probably Approximately Correct Learning Theory, or PAC learning Theory, provides a mathematical definition of what machine learning is. It is the theory behind how we can create and use models of a data set for classification and regression problems in a supervised machine learning setting. It is what describes how the machine learns from examples in mathematical form. The theory answers whether there’s an algorithm which can produce a good model when given random data.

The official definition of PAC Learning is:

Let X be a set, and \mathsf{C} be a concept class over X. We say that \mathsf{C} is PAC-learnable if there is an algorithm A(\varepsilon, \delta) with access to a query function for \mathsf{C} and runtime O(\textup{poly}(\frac{1}{\varepsilon}, \frac{1}{\delta})), such that for all c \in \mathsf{C}, all distributions D over X, and all inputs \varepsilon, \delta between 0 and 1/2, the probability that A produces a hypothesis h with error at most \varepsilon is at least 1- \delta. In symbols,

\displaystyle \textup{P}_{D}(\textup{P}_{x \sim D}(h(x) \neq c(x)) \leq \varepsilon) \geq 1-\delta

where the first \textup{P}_D is the probability over samples drawn from D during the execution of the program to produce h. Equivalently, we can express this using the error function,

\displaystyle \textup{P}_{D}(\textup{err}_{c,D}(h) \leq \varepsilon) \geq 1-\delta 1

I don’t expect most individuals who don’t have a mathematical or computational learning theory background to understand any of the above, so below is my attempt to redefine the above in Layman’s terms, removing the math, and adding familiar data science/machine learning terms:

“For the true underlying function that represents our data set to be considered “PAC learnable” (i.e. can we learn to approximate this true function), the machine must be able to come up with a model such that the error between the model and the true concept is within an acceptable range of error (approximately correct) with a predefined level of confidence, and can most of the time (high probability) stay within that acceptable error given new data sets.”

Lets break this down:

We start with some data (for simplicity, lets look at a single explanatory variable x and our predictor variable y). If we wanted to determine the relationship between these two variables, we could run a regression. All a regression does is give us a model to describe this relationship to the best of its abilities. Furthermore, we could use this model to help predict future y’s given new data sets of x, to the best of the model’s ability. A model that was created using training data (by splitting our data into a training set and testing set) will not be 100% accurate in reflecting the whole data set, but it approximates the relationship between the X and Y. We can improve our models approximations by reducing the error (residuals) between our model and what the training data shows (we consider this problem “PAC learnable” if we can reduce this error within acceptable bounds) If this model does a good enough job at approximating the true relationship between the data, we would expect with high probability that it would continue to do a good job predicting the y variables with new data sets (this is where the test set comes in).

What I described above was a high level understanding of what a regression is, and shouldn’t be unfamiliar to individuals with machine learning experience. But what I also attempted to described is the key concepts to what makes PAC learning theory integral to machine learning, by weaving the theory into the example. Hopefully this helps shed some light on what PAC learning is and how it is used and understood within the Machine Learning framework.

 

 

 

Reference:

1 HTTPS://JEREMYKUN.COM/2014/01/02/PROBABLY-APPROXIMATELY-CORRECT-A-FORMAL-THEORY-OF-LEARNING/




