## Webscraping and Subreddit Categorization

### Repository Organization:

README.md: Executive Summary
<br>
Webscraping-Climbing-&-Yoga-Subreddits.ipynb:
<br>
- Scrape data from Reddit API
<br>
Subreddit Text Analysis-Climbing-Yoga.ipynb:
<br>
- Reads in csv containing scraped data
- Clean and Transform Data
- Fit data to models
- Observe most indicative features and evaluate model performance

### Summary:
The purpose of this analysis is to demonstrate successful methods and models to re-create lost subreddit categories for Reddit.com, a social news aggregator.
<br>
As a initial case, I chose two subreddits: /r/yoga and /r/climbing to find the top words that categorize a subreddit post and use those to predict the categories for future posts. The tops predictor words for the yoga subreddit  were "comp" and the word "yoga" itself. Similarly for climbing, the top word was "climb", "gym", and "boulder".
<br>
To gather the data I need, I used webscraping to pull data into json format from Reddit’s API.
<br>
Once I had sufficient data (approximately 1500 rows), I converted words to root words using EnglishStemmer I transformed the text data into  the titles and body of the posts using CountVectorizer, which counts the frequency of words and return the words that have the highest frequencies: CountVectorizer.
<br>
Finally, I Modeled the data using 3 classificaiton models:
KNN Classifier, Logistic Regression and Random Forest Classifier. Logistic Regression and RandomForest had the highest accuracy scores on both train and test data. Tuning number of neighbors for KNN and max_depth (using GridSearch) for Random Forest raised the test scores and brought the test and train scores closer, reducing overfit.

<br>
Finally, in order to categorize these and other subreddits, I would suggest using RandomForest, as it had high accuracy score on both train and test data and Logistic Regression, in order to view top predicting words (and also had the highest train and test accuracy scores).

Since other reddits  may not be as clearly differentiable, additional methods we could apply include the folllowing:ngrams, TF-IDF Vectorizer and adding or engineering additional features. ngrams can be altered to include multiple words and TF-IDF is a method that returns of proportion of frequency for word features. Additional features could include whether the post has pictures, the number of comments or the number of upvotes it has, or the length of the title or body of the post.
