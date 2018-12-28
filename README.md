# Stance Detection for Identification-of-Fake-News


We try to tackle the issue of fake news using Artificial Intelligence and Machine Learning. According to [fakenewschallenge.org](fakenewschallenge.org), first step towards identifying fake news is to see what other news sources are talking about the same news.

We use the dataset provided by fakenewschallenge.org. The task is to identify whether the given body is 'related' or 'unrelated' to the title. If related, does it 'discuss', 'agree', 'disagree', with the given title.

I have referred the approach of Benjamin Riedel et al. mentioned in their [paper](https://arxiv.org/abs/1707.03264) - "A simple but tough-to-beat baseline for the Fake News Challenge stance detection task". The approach uses a sinlge layer neural network as a classifier. The features are identified as concatination of TF-vector of Headline, TF-vector of Body, and TF-IDF cosine similarity between the headline and the body.

The mentioned apporach has been optimized for getting a good score on fakenewschallenge.org's scoring system. As the scoring system gives more weightage to the distinction between 'Unrelated' and 'Related', the accuracy of the mentioned approach is high for 'Unrelated' classes. It is very low for 'disagree' (6.6%) labelled data. I have tried to improve the algorithm to perform equally on all classes. 

I have used undersampling and oversampling techniques to balance the training data. Further, I have given class weights to specify to the model that classification of all classes is equally important.
