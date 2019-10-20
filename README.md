# Netflix_movie_recimendation
## 1.1 Problem Description
Netflix is all about connecting people to the movies they love. To help customers find those movies, they developed world-class movie recommendation system: CinematchSM. Its job is to predict whether someone will enjoy a movie based on how much they liked or disliked other movies. Netflix use those predictions to make personal movie recommendations based on each customer’s unique tastes. And while Cinematch is doing pretty well, it can always be made better.

Now there are a lot of interesting alternative approaches to how Cinematch works that netflix haven’t tried. Some are described in the literature, some aren’t. We’re curious whether any of these can beat Cinematch by making better predictions. Because, frankly, if there is a much better approach it could make a big difference to our customers and our business.

Credits: https://www.netflixprize.com/rules.html
## 1.2 Problem Statement
Netflix provided a lot of anonymous rating data, and a prediction accuracy bar that is 10% better than what Cinematch can do on the same training data set. (Accuracy is a measurement of how closely predicted ratings of movies match subsequent actual ratings.)

## SUMMARY:
Netflix movie recomdation is itslef a very complex problem to solve. This implementation is based on the rasearch paper Factor in the Neighbors: Scalable and Accurate Collaborative Filtering written by Yehuda Koren.
The metric which is used in this problem is RMSE(Root Mean square error). This metric mesures the diffrences between the values predicted by the model and actual values observed.
step-by-step procedure taken to solve this problem:

### CHAPTHER-1: Data loading

The data itself comes with four txt files. so, write all the data into data.csv file and read the data into pandas dataframe\

Check weather any null values and duplicates are present in the data.

Split the data into 80:20 and write into train.csv and test.csv files.

### CHAPTHER-2: Exploratory data analysis

Analysis of rating is performed.

Analyzing no.of raing given in a month.

Adding new column day of the week.

Analyze ratings given by user by ploting pdf and cdf.

Creating a sparse matrix for train and test data. where columns are movies and rows are users.

Getting the global averages of movie rating rated by each user and avreage rating rated per movie.

### CHAPTER-3: Computing Similarity Matrix

Computing movie-movie similarity.
### CHAPTER-4: Implementing Models:

This problem can be posed as both recomendation and regression problem.

So, we use XGBRegressor suprise libary to slove this problem.

First, sample the data because solving this problem is a non-trival task and featurize the data for both regression and suprise libary.

### Steps:

Preform XGBRegression using fraturized regression data.

perform SupriseBaseLine model on featurized suprised libary data.

ADD the output of the baseline model as a feature of regression data and perform regression data.

perform SupriseKNN for user-user and item-item.

The output of the both user-user and item-item is add to the regression data and XGBregressor is performed.

Perform matrixfatorization of SVD and SVD++ add the output is added as a feature to the regression data.

By droping Suprisebaseline feature XgbRegressor is performed.

Finally, by taking all the data XGBRegressor is performed.
