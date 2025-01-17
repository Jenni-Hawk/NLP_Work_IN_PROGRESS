# NLP_TopicModeling
This was my first Natural Language Processing / Topic Modeling project using a breadth of classic NLP algorithms. 
A follow up to this project that implements advanced, modern-day techniques can be found [here](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling_Tweets/blob/main/README.md). 

# Client / Background
- Since Twitter is a major conversation platform, The Washington Post would like to understand the topics that are trending within the January 6th Committee Hearings to get potential story ideas.

# Key Questions to Answer
- What topics were tweeted about during the Oct 13th hearing?
- What was the sentiment of the conversation?

# Data
- 35,000 Tweets / Retweets

# Solution Path
The approach was to use several different algorithms to determine which most clearly uncovers the different topics within the tweets. VADER sentiment ananlysis was applied to determine how it interprets the sentiment of the conversation.

#### [Get Tweets + Data Clean](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/1_Acquire_Data_PreProcess.ipynb)
- Utilized Tweepy Python library to access Twitter API and acquire tweets
- Removed special characters, punctuation, etc

#### Preprocess the Text Data
- Tokenize
- Remove Stop Words
- Vectorized in two ways: 
  * **CountVectorizer:** Counts the number of times a word appears in a document (bag-of-words)
  * **TF-IDF Vectorizer:** The percent of the document that consists of a particular term (Term Frequency) AND heavier weighting of rare words. Use this approach because some words are better distinguishers of the documents than just highest freqency words. 
  
#### Topic Modeling 
Implemented matrix factorization and probabilistic algorithms along with different vectorizing approaches to determine which can result in best topic clarity:
- [LSA with CountVectorizer & LSA with TF-IDF](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/2_TopicModel_LSA_CountVec_TDIF.ipynb)
- [LDA with CountVectorizer](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/3_TopicModel_LDA_CountVec.ipynb)
- [LDA with Bigrams](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/4_TopicModel_LDA_Bigrams.ipynb) Utilized Gensim Phrases()
- Strategic Approach to Bigrams:
  * Based on my human, cursory review of the tweets I didn't see two word (or more) statements that were being used to communicate a specific idea within the tweets. I wanted to see what a bigram algorithm could discover, therefore I kept the algorithm arguments broad. Also, being new to Phrases() I wanted to see what it could do with defaults and broad hyperparameter selections.  
  * After reviewing some initial bigrams, I did extend the stop word list for this algorithm

#### Sentiment Analysis with VADER
- [Applied to entire conversation and individual topics determined by LSA Topic Modeling](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/5_Sentiment_Analysis.ipynb)
- Analyzed how VADER was interpreting the conversation. From a human perspective, were the negative and positive scores making sense? 

#### Findings
Check out the [presentation](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/NLP_Presentation.pdf)

#### Tech Tools Used
- Tweepy
- NLTK
- Sklearn
- Gensim
- VADER
- Regex
- Pandas

