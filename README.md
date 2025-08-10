# Fake-News-Detection
This project uses a Bidirectional LSTM to spot fake news by checking the text. With fake stuff spreading super fast on social media, this tool helps people figure out if news is real or not. 
Fighting misinformation one model at a time!

## Overview
This project implements a Fake News Detection System using a Bidirectional Long Short-Term Memory (BiLSTM) network. The model is trained on the Fake News Detection dataset by Bhavik Jikadara (available on Kaggle) to classify news articles as either fake or real.

The approach combines Word2Vec embeddings with the sequential learning capabilities of Bi-LSTMs to capture semantic meaning and contextual relationships in text.

## Dataset
Source: Fake News Detection by Bhavik Jikadara on Kaggle (https://www.kaggle.com/datasets/bhavikjikadara/fake-news-detection )

### Structure: Two CSV files — fake.csv and true.csv.
Class Labels:
0 → Fake news
1 → Real news

### Note: Due to file size limitations, the dataset is not included in this repository. You can download it directly from Kaggle or enable the Kaggle API in your environment to fetch it automatically.

## Data Preprocessing
-Visualized subject distribution using pie charts.

-Created bar plots of the most frequent words.

## Cleaning (clean_text function)
-Converted text to lowercase.

-Removed backslashes, hyphens, email addresses, Twitter handles, and URLs.

-Removed accented characters and special characters (kept only letters and numbers).

### Merging and Labeling
-Concatenated title and text columns.

-Removed publisher metadata from real news.

-Combined both datasets with class labels.

## Tokenization & Embedding
-Tokenized text using Keras Tokenizer.

-Trained Word2Vec model (vector_size=100, window=10).

-Created an embedding matrix for the model’s embedding layer.

### Model Architecture
-Embedding Layer: Pre-trained Word2Vec vectors (non-trainable).

--Bidirectional LSTM Layer: 128 units, dropout 0.2, recurrent dropout 0.2.

Dense Output Layer: 1 neuron with sigmoid activation for binary classification.

