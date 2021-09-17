# Language Identification Task

## Problem statement

This project aims to develop a machine learning model that classifies the given passage to the language it belongs to.

## Data

Reference - kaggle
https://www.kaggle.com/zarajamshaid/language-identification-datasst

## Approach

### Calculating Features

Count vectors of character level n-grams for a range upto 4 of input text is used as features. Converting the input text to n-gram is called tokenization.

For example, the features for word  ′𝑚𝑎𝑡𝑐ℎ′  are  𝑚,𝑚𝑎,𝑚𝑎𝑡,𝑚𝑎𝑡𝑐,𝑎,𝑎𝑡,𝑎𝑡𝑐,𝑎𝑡𝑐ℎ,𝑡,𝑡𝑐,𝑡𝑐ℎ,𝑐,𝑐ℎ,ℎ .
Countvectorization is the most basic method of transforming words into vectors by counting occurrence of each character ngram in each document. The output is a document-term matrix with each row representing a document and each column addressing a token (weight assigned to each token based on counting the occurence).

We use training data to build vocabulory for count vectorization.

### Model

Random forest model is used for classification. The model is validated using k-fold cross validation.
