#Quora-Question-Pairs
##Model to identify duplicate questions in Quora, Can you identify question pairs that have the same intent?

#Business Problem
A place to learn and share knowledge about anything is Quora. It serves as a forum for questions and connections with experts who offer insightful observations and thorough responses. People are better able to understand the world and learn from one another as a result.
It's not surprising that many questions on Quora are similar in wording given that over 100 million people visit the site each month. Multiple questions with the same intent can make readers feel as though they must respond to various versions of the same question, while also making seekers spend more time looking for the best solution to their problem. Canonical questions are highly valued on Quora because they offer active writers and seekers a better experience and more long-term value.

#Problem Statement
Identify which questions asked on Quora are duplicates of questions that have already been asked.
This could be useful to instantly provide answers to questions that have already been answered.
We are tasked with predicting whether a pair of questions are duplicates or not.

#Real world/Business Objectives and Constraints
The cost of a mis-classification can be very high.
You would want a probability of a pair of questions to be duplicates so that you can choose any threshold of choice.
No strict latency concerns.
Interpretability is partially important.
