# Book Recommendation System

## Problem Formulation 📚
This project presents a content-based book recommender system that utilizes natural language processing (NLP) and machine learning (ML) techniques to offer personalized book suggestions based on book summaries. By analyzing book summaries, the system identifies similarities and associations between books, ensuring accurate and relevant recommendations. The goal is to connect readers with books that match their interests, enhancing their reading experience and promoting literature exploration in the digital age.

## Data Preparation 📊
The dataset comprises 16,559 entries with 7 columns:
- Wikipedia ID: Unique identifier for each book from Wikipedia.
- Freebase ID: Unique identifier for each book in the Freebase database.
- Book Title: Title of the book.
- Book Author: Name of the book's author.
- Pub Date: Publication date of the book.
- Genres: Genres associated with the book.
- Summary: Brief summary of the book.

The data preparation involved:
- Handling missing values by dropping rows with null values in the Genres column.
- Word count extraction for the Summary column.
- Conversion of the Genres column from JSON format to a list of genres.
- Due to memory limitations, a random sample of 1000 rows was selected for further processing.

## Text Feature Engineering 🔍
Text feature engineering included:
- Lemmatization using WordNet.
- Tokenization, lowercase conversion, stop word removal, and lemmatization based on parts of speech for the summary text data.

## Clustering 📊
The K-Means algorithm was employed for clustering:
- Determination of the optimal number of clusters using the elbow method.
- Visualization of clusters using TSNE.
- Observation of some separation between different clusters.

## Classification 📋
Classification involved:
- Preparation of the target column (Genres).
- Utilization of cluster labels as new genres due to multiple values in the Genres column.
- Classification using five different models.

## Chatbot 💬
An interactive chatbot was developed with two options:
- Recommendation by book name.
- Recommendation by genre.
Integration with Dialogflow was achieved via ngrok to establish a secure connection. Recommendations were provided based on book titles or genres, with fallback options for unmatched queries.

## Chatbot Performance 🚀
The chatbot demonstrated satisfactory performance in pretrained scenarios. It accurately recommended books based on specified genres or book titles from the dataset. However, its performance weakened when prompted with inputs not present in the dataset due to limited training data.

## Innovativeness 🌟
Innovative techniques were applied to handle the complexities of the Genres column, including data preprocessing, feature engineering, and clustering. Conversion of JSON data to a list of genres, coupled with clustering and label assignment based on frequent genres, resulted in a dataset with 5 unique labels, simplifying classification based on book summaries.

---

### Team Members 👥
- Ahmed Badawy
- Anas Elbatra
- Esmael Ezz
- Yousef Shindy
