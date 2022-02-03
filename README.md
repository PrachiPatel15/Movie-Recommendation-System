![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/wordcloud(film).png)

# Movie-Recommendation-System: Project Overview
- This project has two main objectives.
- One of the main objective is to create a recommendation system to give users the opportunity to watch movies similar to the one they have previously watched and second is   to create an IMDb rating prediction system. In that way, when a new movie is going to be released, its IMDb rating can be predicted.
- At the beginning data merging and data cleaning was performed.
- After that, various EDA analysis were applied as well as Spearman and Pearson Correlation was performed to see the correlated features.
- We implemented 2 unsupervised machine learning algorithms, those  are Cosine Similarity and K-means clustering for the recommendation system.
- And then we implemented 3 supervised machine learning algorithms for IMDB rating prediction system. Two of them are classification algorithms which are KNN and Random Forest classification.
- Then, we tried to determine the best algorithms for both recommendation and prediction systems.

# Code and Resources Used
- ***Python Version:*** 3.8
- ***Packages:*** pandas, numpy, sklearn, matplotlib, seaborn
- ***Dataset:*** Netflix: https://www.kaggle.com/shivamb/netflix-shows
                 IMDb data: https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset

# Data Preprocessing
- First we loaded both the dataset 'netflix_titles.csv' and 'IMDb movies.csv'.
- In order to recommend the movie and shows we merged both the dataset.

# Data Cleaning
- Firstly, dataset was containing some duplicate values so we dropped them.
- Also dataset has plenty NULL values so it needed to be dropped where it has high null values and some of the less containing null columns were filled with some values.

# Exploratory data analysis
- We looked at the top 10 TV shows and Movies by their ratings.
- We plotted different pie-charts, bar-graphs and box plots showing how the content of Netfix is distributed according to Age, how the ratings distributed and contents by their Genre respectively. Below are some glimps of them
  - ![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/contents(genre).png)![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/ratings.png)
- 
