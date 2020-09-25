# Udacity-ML-Nanodegree-Projects

# OVERVIEW
This repository contains the two main projects completed during my Udacity Machine Learning Nanodegree Program. My additional final Capstone project on stock prediction is in a different repository [here](https://github.com/jfarrell8/Udacity-Machine-Learning-Capstone). Below I've detailed each project problem, and the general process about how I went to analyze each problem. Further details for each project can be found within their respective folders/Python notebooks.
________________________________________________________________________________
***Plagiarism Detector Project***

In this Plagiarism Project I was tasked with building a plagiarism detector that would examine some sample text files from a modified version of Clough and Stevenson's dataset [Plagiarised Corpus](https://ir.shef.ac.uk/cloughie/resources/plagiarism_corpus.html) and perform binary classification. Source text would be provided, and the model would then predict whether a provided file is plagiarized or not.

I attacked the problem by looking at similarity features, specifically containment and longest common subsequence.

**Containment:** 
Counts up the total number of words or phrases, or "n-grams", that are the same in the source and answer text. Where n=1 for an n-gram, I will look at only *words* as comparison. If n=2, then we'll be comparing *2-word sequences*. Using count vectorization for n-grams of a source and answer text, containment can be expressed by the following formula:

![equation](https://latex.codecogs.com/gif.latex?\frac{\sum{count(\text{ngram}_{A})&space;\cap&space;count(\text{ngram}_{S})}}{\sum{count(\text{ngram}_{A})}})

If the two texts have no n-grams in common, the containment will be 0, but if all their n-grams intersect then the containment will be 1. Intuitively, you can see how having longer n-gram's in common, might be an indication of cut-and-paste plagiarism.

**Longest Common Subsequence:**
From Clough and Stevenson's paper, the longest common subsequence is the longest string of words (or letters) that are the same between the Wikipedia Source Text (S) and the Student Answer Text (A). This value is also normalized by dividing by the total number of words (or letters) in the Student Answer Text.

There are two notebooks in this project:
1. Building features to train the model on: Containment and LCS
2. Train the model and evaluate

______________________________________________________________________________________

***Sentiment Analysis Project***

The purpose of this project was to get familiar with Amazon's SageMaker by building a custom PyTorch recurrent neural network (RNN) to determine the sentiment (positive or negative) of a movie review from the [IMDb dataset](https://ai.stanford.edu/~amaas/data/sentiment/).

I trained the custom RNN model using a modified tokenized bag-of-words feature set, deployed an endpoint, and evaluted a new review within the notebook. I took this one step further by creating a simple web app using an API Gateway and a Lambda function to predict review sentiment.
