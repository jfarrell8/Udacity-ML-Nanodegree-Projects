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

__________________________________________________
