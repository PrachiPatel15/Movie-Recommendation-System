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
- ***Dataset:*** Netflix: https://www.kaggle.com/shivamb/netflix-shows IMDb data: https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset

# Data Preprocessing
- First we loaded both the dataset 'netflix_titles.csv' and 'IMDb movies.csv'.
- In order to recommend the movie and shows we merged both the dataset.

# Data Cleaning
- Firstly, dataset was containing some duplicate values so we dropped them.
- Also dataset has plenty NULL values so it needed to be dropped where it has high null values and some of the less containing null columns were filled with some values.

# Exploratory data analysis
- We looked at the top 10 TV shows and Movies by their ratings.
- We plotted different pie-charts, bar-graphs and box plots showing how the content of Netfix is distributed according to Age, how the ratings distributed and contents by their Genre respectively. Below are some glimps of them

   ![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/contents(genre).png)![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/ratings.png)
 
- I also plotted scatter plot showing relation between votes and ratings, duration and ratings, duration and country etc.

   ![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/duration(ratings).png)

# Encoding
- I performed encoding to convert the columns that have string values into columns that have integer values in order to use these columns in the algorithms that needs integer values in features.
 - With the help of Sklearn's OrdinalEncoder I converted them into integer.

# Correlation
- Now the data has all the numerical data we can plot how each attribute is connected with another.
- For that I've considered pearson's and spearman's correlation.

   ![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/correlation.png)

# Machine Learning Models
- I've used two different model building techniques for both the perposes.
  1. Unsupervised Models(recommendation system)
  2. Supervised Models(IMDb rating prediction system)
- I've first vectorize some of the left attributes in order to use them into machine learning models.
> Unsupervised Models:
  - KMeans:
     - K-means is a unsupervised clustering algorithm. We performed k-means clustering in order to cluster similar movie and tv shows together.
     - I chose Elbow method and got how many clusters I need to take in order to get the best output
     - then did some __dimensionality reduction__ using PCA.
     - KMeans worked pretty well on the dataset.
     
       ![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/KMeans.png)
       
  - Cosine Similarity:
     - In cosine similarity, for each row based on their Title we put 10 columns (Duration, Country, Language, Director, Description, IMDb Rating, Cast, Year, Rating, Genre) into one column ("All Columns") to represent our bag of words.
     - Then created cosine similarity matrix and got result which was giving the recommendation.
     
       ![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/cos_sim.png)
> Supervised Models:
  - Random Forest
    - Accuracy: 63%
    - To improve our algorithm's performance and increase the accuracy, we used different methods such as using hyperparameters and using some important features too.
    - By using GridSearchCV We got 62% accuracy on RF algorithm.
    
  - KNN:
    - First defined some new columns in order to get optimised result.
    - Then did vectorization on string containing columns.
    - Divided dataset into three parts - __train set, validation set, test set__
    - Applied KNeighborsClassifier and got accuracy: __54%__
  
  - Linear Regression:
    - Accuracy: __60%__
 
 - We took all the algorithms and measured __MSE, MAE, rMSE__ and compared them.
  - The best result among all the three models was from __RANDOM FOREST(62%)__.

- Lastly we did accuracy comparison of Random Forest and KNN.
  ![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/accuracy_comp.png)

- Error comparison of all the models.
  ![](https://github.com/PrachiPatel15/Movie-Recommendation-System/blob/main/error_comp.png)
  
# Conclusion
- According to the results of the implemented algorithms that mentioned above, both the film recommendation and IMDb prediction systems are working in a some extent.
- Taking everything into consideration, For IMDb prediction algorithms, in clasification part, at first both KNN and RF have close accuracies but after implementing the conter vectorizer, we saw that RF gives a higher accuracy value. For the regression, we concluded that linear regression was performed better when we compare it with KNN, RF and Decision Tree regressions. Also, for our recommendation systems cosine similarity performed better than k-means.
- For our recommendation systems, cosine similarity's results are more consistent.
