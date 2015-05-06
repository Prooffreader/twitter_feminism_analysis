# The most characteristic words in pro- and anti-feminist tweets #

## Attitude analysis by machine learning as an alternative to sentiment analysis in order to classify tweets as pro- or anti-feminist, and determine the differences in their vocabularies ##

#### This project won the Data Science prize andthe  NLP prize at the Montreal Big Data Week Hackathon 2015 #

By David Taylor, Zafarali Ahmed, Jerome Boisvert-Chouinard, Dave Gurnsey, Nancy Lin, and Reda Lotfi

For a blog post about the results: http://www.prooffreader.com

For a blog post about the methodology: http://prooffreaderplus.blogspot.ca

---

OUTLINE:

* We used the Twitter Search API from January to April, 2015 to search twitter periodically (at random intervals as short as 15 minutes) for the last tweets containing the terms 'feminist', 'feminists' and 'feminism' (usually the last 100 tweets, but at random intervals once every few days, the last 1500 tweets). 
* A CSV file was made of the search results resulting in about 988,000 tweets. Retweets and duplicate tweets (i.e. coming from a 'share this' button on a website) were removed, with the justification that we are studying the words humans choose to actively employ in tweets; simply clicking a button to retweet or share does not involve authorial word choice on the part of the tweeter.
* We manually curated approximately 1,000 randomly chosen tweets into the following three categories: 'pro-feminist' (1), 'anti-feminist' (-1), 'neither' (0). This involved some reflection, to try to intuit the underlying attitude of the tweet's author. When in doubt, for example if the tweet was news reporting or if it may have been sarcastic, we defaulted to class 0.
* We tokenized the tweets (broke them up into separate words and symbols) with almost no stopwords, with the justification that in only 140 characters, every token matters.
* We verified that sentiment analysis was not up to the task of predicting our attitude classes, so we used a Naive Bayes classifier to predict the attitudes of the other 390,000 tweets.
* We used the log-likelihood method to determine which words or tokens were most characteristic ('key') to each of the pro- or anti-feminist (+1 or -1) attitude classes.
