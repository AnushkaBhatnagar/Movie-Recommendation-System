# Movie-Recommendation-System
## **Description:**

The goal is to develop a movie-recommendation system that suggests the user top-10 most-suited options based on the movie name they enter. The system uses correlation between the ratings assigned to different movies to find similarities between them, and generates the recommendation list based on the calculated correlation coefficient for each pair (from most highly correlated to least correlated).

## **Datasets Used:**

Two datasets (one for movie details and one for movie ratings) have been used. Both datasets have been uploaded in the github repository, named *movies.csv* and *ratings.csv*. The datasets were downloaded from the following link: https://grouplens.org/datasets/movielens/latest/ 

## **Methodology:**

The implementation has been carried out in Python on Google Colaboratory. NumPy, Pandas and Matplotlib have been used for building and executing the project.

After importing the desired libraries and reading the csv datasets, the datasets are merged, combining the movie names and ratings based on the movie id. The movie names are first grouped by the average of their total ratings on a scale of 5, and then by the total 'number' of ratings each received. The data is sorted in descending order for convenience. 

We plot a histogram for the number of ratings and see that the majority of the movies received less than 50 ratings, while very few had over 100 ratings. Upon plotting a histogram for average ratings, we deduct that there may be outliers in our data, for it seems to have a weak normal distribution. A joint plot shows us that movies with average higher ratings have more 'number' of ratings as well. Thus, we see that a well-rated and well-known movie is generally watched by more people.

Finally, we ask the user to input a movie name. If the name entered is not present in the dataset, a message stating its unavailability is displayed. If the name entered has only one rating available, a message describing the insufficiency of data for making recommendations is displayed. Otherwise, the system generates a list of top-10 most-suitable movie names, along with their correlation coefficient with the input and number of ratings for the movie.

## **Assumptions:**

1. It is assumed that the user enters the correct and full movie name as is registered on the database, and makes no typographical errors, as the system is not equipped with overlooking misspelled inputs and generating suggestions for the same.
2. It is assumed that the user is entering a movie name which is present in the database in order to get the recommendations. Otherwise, the system displays a message stating that the entered movie is not available.
3. In case a movie has only one rating listed, then making a correlation matrix for it, and hence generating suggestions would not be possible. Hence, in such a scenario, the system would display a message stating that it has insufficient data (ratings) available at present to make any deductions.
4. It is assumed that the user would treat the correlation column in the output as the percentage matched, that is, a correlation of 1.00 would mean that there is a 100% match.
