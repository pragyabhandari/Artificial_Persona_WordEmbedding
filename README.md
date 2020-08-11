# Artificial Health Persona with Word Embeddings

## Business Objective

The objective of this project is to create an artificial personality for understanding the relevance of online articles with different consumer groups i.e. Health conscious group of individuals in this case. Such an algorithm may help marketing companies to identify their target consumers and discover new avenues for investment that may maximize ROI.

# Overview

The algorithm has been created using WordNet word embedding which is a knowledge-based measure. It quantifies semantic relatedness of words using various semantic networks such as synonyms, hypernyms, hyponyms, holonyms and meronyms. Therefore, wordnet uses word hierarchies to calcuate similarity score between the words of a sentence. In this project, we have used the Wu & Palmer, also known as WUP Similarity, as it is a better metric that measures the semantic similarity of two concepts as their depth of the least common subsumer in a large corpus. Below is the high-level approach used:

- Accepts an arbitrary message as input
- Tokenize by splitting the message into individual words
- Use WordNet to translate each word into an embedding
- Compute similarity relative to a set of words related to Health subjects

## Model Evaluation Metric

The model is evaluated by calculating a ***Lift Score*** for every word in a sentence (i.e. the input). In a ***Lift Score Analysis***, we iteratively delete one word from our message and then subtract the resultant similarity score from the original or the baseline interest score. It, therefore, tells the significance of each word in our message. If the lift score is negative, it implies that the new score is higher and the removed word has a positive impact on the interest score. Similarly, a positive lift score indicates that deleting a word from a message, reduces the new interest score and has a positive impact on the overall similarity score.

## Visualization

Based on the calculated lift scores, we have divided our message into positive and negative words. These positive and negative words are then plotted on a bar graph corresponding to their respective lift scores. The visualization will, hence, help us to gain understanding of how each word in each of the messages impacts the baseline interest score.

# Dependencies

To run this algorithm, we require the following:

- Numpy
- Pandas
- NLTK
- Matplotlib
