## Webscraping and Subreddit Categorization
### Using Natural Language Processing and Classification Models

### Repository Organization:
<br>
Reddit data:
<ul>
  <li>scraped data from Reddit API and output from modeling</li>
</ul>
Webscraping-Climbing-&-Yoga-Subreddits.ipynb:
<ul>
  <li>Scrape data from Reddit API</li>
</ul>
Subreddit Text Analysis-Climbing-Yoga.ipynb:
<ul>
  <li>Reads in csv containing scraped data</li>
  <li>Clean and Transform Data</li>
  <li>Fit data to models</li>
  <li>Observe most indicative features and evaluate model performance</li>
</ul>

### Executive Summary:
The purpose of this analysis is to demonstrate a model that re-creates lost subreddit categories for Reddit.com, a social news aggregator.
<br>
<br>
As a initial case, I chose two subreddits: /r/yoga and /r/climbing to find the top words that categorize a subreddit post and use those to predict the categories for future posts. The tops predictor words for the yoga subreddit  were "comp" and the word "yoga" itself. Similarly for climbing, the top word was "climb", "gym", and "boulder".
<br>
<br>
Data Collection: <br>
To gather the data I need, I used web-scraping to pull data into json format from Reddit’s API.
<br>
<br>
Data Transformation:<br>
Once I had sufficient data (approximately 1500 rows), I converted words to root words using EnglishStemmer I transformed the text data into  the titles and body of the posts using CountVectorizer, which counts the frequency of words and return the words that have the highest frequencies: CountVectorizer.
<br>
<br>
Data Modeling & Evaluation: <br>
I Modeled the data using 3 classification models: KNN Classifier, Logistic Regression and Random Forest Classifier. Logistic Regression and RandomForest had the highest accuracy scores on both train and test data. Tuning number of neighbors for KNN and max_depth (using GridSearch) for Random Forest raised the test scores and brought the test and train scores closer, reducing overfit.
<br>
Conclusions:<br>
Finally, in order to categorize these and other subreddits, I would suggest using RandomForest and Logistic Regression. RandomForest had high accuracy score on both train and test data. Logistic Regression made it easy to view top predicting words, and it also had the highest train and test accuracy scores.
<br>
Further Analysis:<br>
Since other reddits  may not be as clearly differentiable, additional methods we could apply include the folllowing: ngrams, TF-IDF Vectorizer and adding or engineering additional features. ngrams can be altered to include multiple words and TF-IDF is a method that returns of proportion of frequency for word features. Additional features could include whether the post has pictures, the number of comments or the number of upvotes it has, or the length of the title or body of the post.
