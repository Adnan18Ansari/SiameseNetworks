# Questions Similarity check
In this notebook we will apply Siamese networks to natural language processing (NLP). We will build a classifier that will allow us to identify whether two questions are similar or not. We will be implementing our library using trax library. Our model will take in the two question embeddings, run them through an LSTM, and then compare the outputs of the two sub networks using cosine similarity. We will be using the Quora question answer dataset to build a model that could identify similar questions.

A Siamese network is a neural network which uses the same weights while working in tandem on two different input vectors to compute comparable output vectors. We get the question embedding, run it through an LSTM layer, normalize 𝑣1 and 𝑣2 , and finally use a triplet loss to get the corresponding cosine similarity for each pair of questions. The Siamese network we are about to implement looks like this:-

   <img width="783" alt="siamese" src="https://user-images.githubusercontent.com/55757910/177485069-49d26def-bfde-4464-939f-bc0e0a7f2732.png">

We will use TripletLoss as our loss function. In case of Triplet Loss, loss is composed of two terms. One term utilizes the mean of all the non duplicates, the second utilizes the closest negative. For us, humans, elements belonging to the same category possess similar characteristics; we, humans, do this type of classification/inference almost every time. Triple Loss Uses the Same logic, i.e., it tries to reduce the distance/deviation between similar things and increase the same between different things.
