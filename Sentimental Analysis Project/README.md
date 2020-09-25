***Sentiment Analysis Project***

The purpose of this project was to get familiar with Amazon's SageMaker by building a custom PyTorch recurrent neural network (RNN) to determine the sentiment (positive or negative) of a movie review from the [IMDb dataset](https://ai.stanford.edu/~amaas/data/sentiment/).

I trained the custom RNN model using a modified tokenized bag-of-words feature set, deployed an endpoint, and evaluted a new review within the notebook. I took this one step further by creating a simple web app using an API Gateway and a Lambda function to predict review sentiment.
