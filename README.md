
# Quora-Question-Pairs
Model to identify duplicate questions in Quora, Can you identify question pairs that have the same intent?

## Business Problem
A place to learn and share knowledge about anything is Quora. It serves as a forum for questions and connections with experts who offer insightful observations and thorough responses. People are better able to understand the world and learn from one another as a result.
It's not surprising that many questions on Quora are similar in wording given that over 100 million people visit the site each month. Multiple questions with the same intent can make readers feel as though they must respond to various versions of the same question, while also making seekers spend more time looking for the best solution to their problem. Canonical questions are highly valued on Quora because they offer active writers and seekers a better experience and more long-term value.

## Description: 
In this problem we have provided two questions with question ID. The task was to determine whether this question are duplicate of one another or not. Data preprocessing and feature engineering was done to get more features. The performance metric used was log-loss. Tried and tested various ML models to get minimum log-loss.

## Problem Statement
Identify which questions asked on Quora are duplicates of questions that have already been asked.
This could be useful to instantly provide answers to questions that have already been answered.
We are tasked with predicting whether a pair of questions are duplicates or not.

## Real world/Business Objectives and Constraints
The cost of a mis-classification can be very high.
You would want a probability of a pair of questions to be duplicates so that you can choose any threshold of choice.
No strict latency concerns.
Interpretability is partially important.

## Data set 
[Click here](https://www.kaggle.com/c/quora-question-pairs/data)

## Machine Learning Probelm
### Mapping the real world problem to an ML problem

Type of Machine Leaning Problem
It is a binary classification problem, for a given pair of questions we need to predict if they are duplicate or not.

Performance Metric
Source: https://www.kaggle.com/c/quora-question-pairs#evaluation

Metric(s):


```bash
  log-loss : https://www.kaggle.com/wiki/LogarithmicLoss
  Binary Confusion Matrix
```

### Train and Test Construction
We build train and test by randomly splitting in the ratio of 70:30 or 80:20 whatever we choose as we have sufficient points to work with.

## Exploratory Data Analysis
### Reading data and basic stats
We are given a minimal number of data fields here, consisting of:



```bash
id: Looks like a simple rowID
qid{1, 2}: The unique ID of each question in the pair
question{1, 2}: The actual textual contents of the questions.
is_duplicate: The label that we are trying to predict - whether the two questions are duplicates of each other.
```

### Distribution of data points among output classes


```bash
Number of duplicate(smilar) and non-duplicate(non similar) questions
```

## Basic Feature Extraction (before cleaning)
### Let us now construct a few features like:




```bash
freq_qid1 = Frequency of qid1's
freq_qid2 = Frequency of qid2's
q1len = Length of q1
q2len = Length of q2
q1_n_words = Number of words in Question 1
q2_n_words = Number of words in Question 2
word_Common = (Number of common unique words in Question 1 and Question 2)
word_Total =(Total num of words in Question 1 + Total num of words in Question 2)
word_share = (word_common)/(word_Total)
freq_q1+freq_q2 = sum total of frequency of qid1 and qid2
freq_q1-freq_q2 = absolute difference of frequency of qid1 and qid2
```

### Analysis of some of the extracted features
Feature: word_share

The distributions of the word_Common feature in similar and non-similar questions are highly overlapping

## Featurizing text data with tfidf weighted word-vectors/tfidf word-vectors
## Machine Learning Models
## Conclusion

| Model             | Tokenizer | Train Log loss | Test Log loss 
| ----------------- | ----------- | -------------| ----------------
| Logistic Regression | TFIDF | 0.44 | 0.44 |
| Linear SVM | TFIDF | 0.45 | 0.45 |
| xgboost | TFIDF | 0.36 | 0.36 |


## Lessons Learned

I believe the most interesting project, I have been come across while learning Machine Learning is the Quora Duplicate Question Problem in which we have a set of questions, and we have to analyze these questions are duplicate or not, so I made XGboost model, to predict they are duplicate or not, and the most interesting part for me is that I had analyzed different NLP techniques.


## Observation:
1. Our aim is to get loss less than Random Model which is 0.8872
2. We Used TF-IDF vectorizer to get better results.
3. TFIDF vector gave better result in each case as compared to TFIDF-W2V
4. The models trained on TF-IDF are not included here
5. XGBOOST tuning 2 gave the best performance with minimum training of 0.158




## Feedback

If you have any feedback, please reach out to us at avasheenshishir@gmail.com







