# Song Hit Predictor

## Project Description

### Motivation

The essence of music is profound, influencing emotions, memories, and identities. The global music industry, generating billions annually, hinges on understanding the elements that make a song popular. Our aim is to unravel these elements, teaching a machine to recognize patterns in hit songs and predict future successes. This machine learning project, focusing on predicting hit songs through their features, including lyrics, is designed to be both fascinating and valuable for music enthusiasts, data scientists, or those exploring machine learning's potential.

### Models and Training

We will be utilizing a comparison approach between multiple models to understand which predicts song hits most effectively. The models in our scope are:

- Logistic Regression
- Decision Trees
- Random Forests

These models will undergo supervised training, ensuring a directed learning process based on our datasets.

### Dataset

Our primary datasets are sourced from:

1. [Billboard Hot-100 Songs 2000-2018w/Spotify Data+Lyric](https://data.world/typhon/billboard-hot-100-songs-2000-2018-w-spotify-data-lyrics) from data.world
2. [Top Hits Spotify from 2000-2019](https://www.kaggle.com/datasets/paradisejoy/top-hits-spotify-from-20002019) from Kaggle

These datasets provide a comprehensive collection of song features, lyrics, and hit statuses spanning nearly multiple decades. We decide to limit our dataset to songs post 2000 as music trends change rapidly and the characteristics that were central to making songs hits also change over time.

## Literature Review

Our project draws inspiration and methodologies from notable studies in the field:

1. ["An Analysis of Classification Approaches for Hit Song Prediction..."](https://arxiv.org/pdf/2301.13507.pdf): This study explores the prediction of hit songs using various machine learning approaches, emphasizing the effectiveness of Logistic Regression and Random Forest models.

2. ["HITPREDICT: Predicting Hit Songs Using Spotify Data"](https://ccrma.stanford.edu/~egeorgie/documents/HitPredict_Final.pdf): A similar venture, this paper details the process of predicting Billboard Hot 100 hits, highlighting the potential application of our research in the music production industry.

3. ["Song Hit Prediction: Predicting Billboard Hits Using Spotify Data"](https://arxiv.org/pdf/1908.08609.pdf): This expansive study focuses on creating a robust dataset for model training, providing insights into effective model training practices.

## Technical Details

### Features

Our models consider various song features for prediction, including but not limited to:

- Acousticness
- Danceability
- Energy
- Liveness
- Valence
- Instrumentalness

### Challenges and Solutions

**Imbalanced Dataset**: Addressed through the Synthetic Minority Oversampling Technique (SMOTE) to balance the dataset. It identifies the class with fewer instances, i.e. the minority class. SMOTE creates synthetic samples by interpolating features between the selected instance and its k nearest neighbors. It randomly selects a specific amount of synthetic samples to generate based on the desired level of oversampling to get a 1:1 ratio between the classes.

**Overfitting**: Mitigated by reducing model complexity, tuning hyperparameters, and selecting the most impactful features, enhancing the model's prediction accuracy.

### Lyrics Analysis

VADER (Valence Aware Dictionary and Sentiment Reasoner) Sentiment Analysis is employed to understand the emotional content within song lyrics, providing additional predictive insight. 

VADER is a lexicon and rule-based sentiment analysis tool. Although there are better techniques for sentiment analysis with the use of NLP now, for a brief understanding of sentiment analysis we can use VADER to get some idea of the sentiment in our case as we do not have labeled data or a trained model for song sentiment classification.

Improving VADER: Currently, the approach of computing the average sentiment of a song solely based on individual word sentiments neglects the contextual and holistic understanding of the lyrics. To enhance the accuracy and depth of sentiment analysis, further consideration should be given to the broader context and overall message conveyed by the lyrics.

## Conclusion

We finalized on using the Random Forest model due to its effectiveness in handling nonlinear relationships and its feature importance insights, both crucial for understanding and predicting hit songs. 

Handling Nonlinear Relationships: Random Forest can capture nonlinear relationships between features and the target variable. In the case of hit song prediction, various factors like tempo, genre, artist popularity, and lyrics can contribute to a song's success, and these relationships are often complex and nonlinear. Random Forest's ability to capture such relationships makes it well-suited for this task.

Feature Importance: Random Forest provides a measure of feature importance, indicating the relevance of each feature in predicting the target variable. In the context of hit song prediction, this can help identify which features have the most significant impact on a song's success. Understanding feature importance can provide insights into the characteristics that contribute to a song's hit potential, allowing for better decision-making and feature selection.

## Setup

To run the project, you need to install the dependencies listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

##  License
This project is licensed under the GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007.