# NBC
My Naive Bayes Classifier for ham/spam message classification.

# Theory
The probability of belonging to a class $Q_k = (ham,spam)$ is calculated using the next formula: $$P(Q_k | x) = P(Q_k)\prod\limits_{i = 1}^n P(x_i|Q_k), $$
where $x$ -  message, $x_i$ - each word in $x$.  

To avoid the problem of unfamiliar words, additive smoothing is used: $$P(x_i|Q_k) = \frac{\alpha + N_{ik}}{\alpha M + N_k}$$

Because of the small values, it is easier to work with logarithms by converting the formula according to the rule of logarithms $\log{ab} = \log{a}+\log{b}:$
$$P(Q_k | x) = \log{P(Q_k)} + \sum\limits_{i = 1}^n \log{P(x_i|Q_k)}.$$

# How to run
You can find file with training set [spam.txt](NBC/src/main/resources/spam.txt) in resources folder. Used data can be found [here](https://github.com/stedy/Machine-Learning-with-R-datasets). All data should consist of two fields: type and message, diveded by **'\t'**.  

In Main file you can change filepath of training set and message variable to classify.

