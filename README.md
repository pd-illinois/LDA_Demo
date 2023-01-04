
## **Demo Twitter Topic Analysis**

* Topic Analysis with Latent Dirichlet Allocation


#### Step 1: Data Scrapping & Storage

**Data Preparation:**

We used SNSCRAPE for capturing the tweets. We captured 20000 tweets from 1st July to 8th November (Midterm Election Day in US).
All the 20000 tweets are available in `data` Folder in `tweets_final.csv`. This is the raw data for our project that we will use. if you are interested in seeing how we scrapped the tweets , please check `source\01_Twitter_scrape.ipynb`

Note that this is a one time activity and data is already downladed and you do not need to run this script again. 
No User sensetive information was captured.
<br/>

#### Step 2: Data Preprocessing

This step is divided into following parts in the file `source\02_Data_Preprocess.ipynb`


Replacing Empty Locations with Unknown
Filtering out Non English Tweets   
Lowercaseing
Removing special characters
Removing Whitespaces
Removing tagged Usernames
Removing Hashtags
Removing RT
Removing URLs and Http tags
Removing Punctuations
Removing Emojis
Stopword Removal
Lemmatization

 
#### Step 3: Exploratory Analysis and Baseline Sentiment Analysis Using VADER

The source file is `source\03_Exploratory_Analysis.ipynb`

*Cleaned Dataset Columns:*

    Date                    Date on which tweet was posted	
    ID                      Tweet ID
    location                Location from where tweet was posted	
    tweet                   Content of the tweet	
    num_of_likes            Number of likes on the tweet	
    num_of_retweet          Number of retweets	
    language                language of the tweet, in our case it's english	
    cleaned_tweets          cleaned tweets by removing the punctuations	and lemmatization

 **Exploratory Data Analysis Results**

 1. What are the words/topics discussed:
 
 ![image2](visualization\label_word_count_y.png)

 
 2. What are the most popular hashtags / words of each tweet type ?
 
 ![image3](visualization\wordcloud.png)
 
 
 For scraping our tweets, we have used the words vote, voting, elections, etc. and we see those are mostly commonly used words in the tweets and all the other words  are related to US midterm elections.
 

#### Step 4 and 5: Train and Build Naive Bayes , KNN and LDA with Model Evaluations
 
**Topic Modeling using LDA**

In NLP , LDA is a Generative Statistical Model , which is based on a distributional hypothesis that similar topics make use of similar words and statistical mixture hypothesis that documents talk about several topics. And such a statistical distribution can be determined (Dirichlet Distribution)
LDA uses an unsupervised learning approach and is a Bayesian Version of PLSA and its parameters are regularized.

We have used Gensim library to build the corpus and dictionary for our LDA model. After multiple iterations and hyperparamterization , we concluded that at 10 topic our model performed at the best with 0.41 Coherance score. The results are discussed in the visualization section and our recorded video.


#### Step 6: Visualizations

**Results Comparison**
        
  *LDA*


  From LDAvis help ,we can visualize the top 10 Topics and how they overlap. The HTML file is available in visualization folder for you to test.
  We see the distribution of words as well the top topics and its relevance in the document.
![image6](/visualization/LDA.png)




#### **REFERENCES**

https://betterprogramming.pub/how-to-scrape-tweets-with-snscrape-90124ed006af
https://github.com/cjhutto/vaderSentiment
Hutto, C.J. & Gilbert, E.E. (2014). VADER: A Parsimonious Rule-based Model for Sentiment Analysis of Social Media Text. Eighth International Conference on Weblogs and Social Media (ICWSM-14). Ann Arbor, MI, June 2014.
https://towardsdatascience.com/evaluate-topic-model-in-python-latent-dirichlet-allocation-lda-7d57484bb5d0
https://stackoverflow.com/questions/48541801/microsoft-visual-c-14-0-is-required-get-it-with-microsoft-visual-c-build-t



