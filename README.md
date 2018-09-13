## Project 3: Reddit Categorization

### Repository Organization:

README2.md: Project Prompt
<br>
Requirements.txt: Project Requirements
<br>
README.md: Executive Summary
<br>
Project-3_Webscraping-Climbing-&-Yoga-Subreddits.ipynb:
<br>
- Scrape data from Reddit API
<br>
Project_3_Subreddit Text Modeling.ipynb:
<br>
- Reads in csv containing scraped data
- Clean and Transform Data
- Fit data to models
- Observe most indicative features and evaluate model performance
<br>
Editted Code.ipynb: code removed from final project, may be useful for further tuning.

### Summary:
The purpose of this analysis is to demonstrate successful methods and models to re-create lost subreddit categories for Reddit.com, a social news aggregator.
<br>
As a initial case, I chose two subreddits: /r/yoga and /r/climbing to find the top words that categorize a subreddit post and use those to predict the categories for future posts. The tops predictor words for the yoga subreddit  were "comp" and the word "yoga" itself. Similarly for climbing, the top word was "climbing" followed by "climb", "gym", and "bouldering".
<br>
To gather the data I need, I used webscraping to pull data into json format from Reddit’s API.
<br>
Once I had sufficient data (approximately 1500 rows) I transformed the text data into  the titles and body of the posts using CountVectorizer, which counts the frequency of words and return the words that have the highest frequencies: CountVectorizer
<br>
Finally, I Modeled the data using 3 classificaiton models:
KNN, Logistic Regression and RandomForest. Logistic Regression and RandomForest had the highest accuracy scores at 93% on the test data.
<br>
Finally, in order to categorize other subreddits, I would suggest using RandomForest, as it had the highest accuracy score on both train and test data and Logistic Regression, in order to view top predicting words.

Since other reddits  may not be as clearly differentiable, additional methods we could apply include the folllowing: Lemmatizer, ngrams, TF-IDF Vectorizer and adding or engineering additional features. Lemmatizer converts words to their root word, ngrams can be altered to include multiple words and TF-IDF is a method that returns of proportion of frequency for word features. Additional features could include whether the post has pictures, the number of comments it has, or the length of the title or body of the post.

In any case, I have many tools with which to analyze the text of subreddits to get the popular site up and running once again!
