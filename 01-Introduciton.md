# Introduction - What is Machine Learning?
A field of study that gives computers the ability to learn without being explicitly programmed.

A computer program is said to learn from experience E with respect to some task T and some performance measure P, if its performance on T, as measured by P, improves with experience E.

#### Example 1: An email program that watched which emails you do or do not mark as spam:
* Experience - Watching you label emails as spam or not spam
* Task - Classifying emails
* Performance - The number or fraction of emails correctly classfiied as spam/ not spam

#### Example 2: A program to to beat a user in a game of checkers:
* Experience - Playing many games of checkers
* Task - The task of playing checkers
* Performance - The probability that the program will win the next game

Different types of Machine Learning algorithms:
* Supervised Learning
  * You teach the computer how to do something
* Unsupervised Learning
  * Let the computer learn by itself

Another type is Reinforcement Learning and Recommender systems, which we will talk about later.

## Supervised Learning
When "right answers" are given to the algorithm. 

### Regression Example
#### Example 1: Housing price prediction

Given a set of data points

This can be found using a **Regression**, which predicts a continuous valued output, which in this case is price.

### Classification Example
#### Example 2: Determing whether breast cancer is malignant of benign

In this example, the data consists of Y/N values.

This would be an example of a **Classification** problem, which predicts a discrete valued output (0 or 1)
* If you wanted to predict if value output is (0, 1, 2, 3), this would also be a classification problem.

In both of the above examples we are using only one or two features. In ML, we can have many.

### More examples:
#### Example 3: You have a large inventory of identical items and want to predict how many of these items will be sold over the next 3 months
Regression problem

#### Example 4: You'd like software to examine individual customer accounts, and for each account decide if the account has been hacked/comprimised
Binary Classification problem

## Unsupervised Learning
Given a dataset that doesn't have any labels, use an algorithm to find structure within the data set

### Clustering Examples
We can derive this structure by clustering the data based on relationships among the variables in the data.

* Genome project
  * Based on user's genes, group them with other similarly typed persons based on the genes they have present
* Organize computer clusters
  * By looking at what machines run together, you can put those computers closer to each other to make the data center run faster
* Social network analysis
  * Given what freinds you associate with the most, can predict what groups of friends associate with each other.
* Market segmentation
  * Allow you to group your customers into different segments so you can market differently to them (think about instagram ads)
    * This example is unsupervised because we don't know in advance what market segment the user is in
* Astronomical data analysis
  * Gives useful theories for how galaxies are formed

### Non-clustering: The "Cocktail Party Problem"
Imagine a party where many people are talking at the same time. If there were only 2 people talking, and 2 microphones placed in seperate locations within the party, these 2 micophones would record different copies of the two speaker's voices.

Cocktail Party algorithm can listen to these recordings and seperate out the two audio voices
