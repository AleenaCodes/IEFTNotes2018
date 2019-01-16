# Lecture 15 - 27 11 18

## Sentiment Analysis

- Understand opinions/views/feelings of a crowd
- Can also be used for prediction
- Less objective than prediction markets, but more widely applicable
- Tries to mine many different resources for data

## Social Data Mining

- There are many sources of social media data that are public
- The web, particularly Twitter provides a lot of real-time information
- This can be used in both 'ordinary' times and 'extrordinary' times e.g. during a wide-scale disaster
- Automated analysis of these sort of data sources can provide useful societal data

## Sentiment Analysis / Opinion Mining

- Sentiment analysis is essentially opinion mining
- There are many sources - twitter, review articles, newspapers, blogs etc.
- 'Smooths out' individual extreme opinions to provide a more general overall opinion
- There are many useful applications -
	- Aggregating 'objective' reviews for a purchaser
	- Tracking concerns about your product - indirect customer feedback
	- Spotting opinions which may impact a stock price
	- Predicting outcomes of events e.g. elections

### Types of Sentiment Analysis

- Document Level - looking at an entire document e.g. a tweet or news article and identifying the overall attitude
- Sentence/Phrase Level - looking at a particular phrase or sentence in a document and identify if it's positive, negative or neutral
- Aspect Level - for an given document identify all the opinions expressed in the document with regards to any aspect of an object

#### Document Level

Supervised approach -

- Simplify classifies a document as 'positive' or 'negative'
- Been around for a while - studies from early 2000's
- A 'bag of words' approach - just all the words, no sense of grammar
- Performed pretty well - 78% using Naïve Bayes, 73% using Support Vector Machine
- Outperformed a human-generated feature set of opinion words
- Not as good as 'traditional' non-opinion machine learning tasks

Unsupervised approach -

- Identify 'interesting' pairs of words using 'part-of-speech' tags (e.g. adjective followed by noun)
- Calculate the Pointwise Mutual Information measure for this pair
	- Probability of them appearing together versus anywhere in the document
	- $\text{PMI}(\text{term}_1, \text{term}_2) = \log_2 \left ( \frac{\text{Pr}(\text{term}_1 \wedge \text{term}_2)}{\text{Pr}(\text{term}_1) \text{Pr}(\text{term}_2)} \right )$
- Probabilites found by counting hits from a search engine
- Top performance - 84% accurate

#### Aspect Level

- A document may contain multiple sentiments about one object
- It can also be useful to see which aspect a sentiment is about
- e.g. "The voice quality is amazing, but it is expensive"

The abstract form of the problem - for a given document (corpus) identify every quintuple of sentiment expressed, consisting of -

1. The object e.g. 'iPhone'
2. The aspect e.g 'Audio quality'
3. The sentiment e.g. positive/negative, possibly a measure of intensity
4. Who holds the sentiment
5. When it was expressed

Steps -

- Aspect extraction
	- e.g. "The voice quality of this phone is amazing" -> ("phone, "voice quality")
	- e.g. "I love this phone" -> ("phone", "general")
- Group aspects into categories
	- Find synonyms for aspects
	- e.g. "battery life" and "battery power" reference the same aspect
- Aspect sentiment classification
- Entity, opinion holder, time extraction
	- Can be straightforward from metadata e.g. timestamp
	- May require Named Entity Recognition

A simple algorithm -

- Mark sentiment words and phrases using a lexicon
	- Positive words get +1, negative words get -1
- Identify sentiment shifters (e.g. 'not', 'never', 'cannot') and swap sentiment values for shifted words
- Identify 'but' phrases
	- If a sentence starts positive, it's likely it's negative after the but (allows analysis for parts of a sentence where sentiment cannot be analysed)
- Sum sentiment scores, weighted by word distance from the aspect word
- This gives an overall +/- sentiment

### Applications

- Automated trading
	- Monitoring microblogs, tweets and investment forums to identify strong sentiment signals to decide if to buy/sell
	- Identify experts among these and weight them more
- Tweet volume and sentiment is used to estimate box office revenues of new movies (see Asur et. al 2010)
- Predicting election result

## Opinion Spamming

- Online opinions have a significant impact
	- e.g. reviews online are important for businesses
	- They can shape policies
- Opinion spamming is the act of organisatons or individuals to influence this impact
	- Fake reviews
	- 'Sock puppet' comments on articles or issues

### Fake Reviews

- These are common - Yelp estimate that they filter around 25% of reviews as they suspect them to be fake
	- Could be owner trying to boost their reputation
	- Could be a fired employee trying to defame a company
- Can be done on a big scale e.g. Samsung recently fined Taiwan for paying people to praise Samsung products and criticise HTC products

### Sock Puppetry

- This is the idea of automating fake news
- Use of many fake personas by one person/organisation to give a misleading impression of an opinion being held widely
- This is a part of 'astroturfing' - when companies try to improve their product rating
- Difficult to spot unless done clumsily
- 'Strawman' sock puppets are used to make a certain view look silly to encourage 'real' posters to generate posts in favour of the view held by the puppeteer

Persona management software exists to make manaing sock pupets easier

- Creates diverse plausible and geographically consistent online personas
- Each have a static IP address assigned
- Puppeteers have randomly selected (geographically diverse) IP addresses which change each day
	- The idea is to blend their traffic with users outside the organisation
- Commissioned by US military in 2011, probably for use in the Middle East

### Opinion Spam Detection

- Spotting opinion spam is difficult and requires effort
- Jindal and Liu (2008) used a supervised learning approach
- They identified duplicate reviews on Amazing (same review, different product/reviewer) as likely fake
- These were used as a training corpus
- They looked at different features -
	- Review features e.g. n-grams, brand-name count
	- Reviewer features e.g. mean and SD of rating give, % of review which were first or only reviews
	- Product features e.g. price, sales rank
- Their results found
	- Negative outlier reviews were heavily spammed, positive outliers less so
	- Singleton reviews were often fake
	- Top-ranked reviewers were more likely to post fake reviews
- However, results are tentative, as the assume that duplicated reviews are fake
	- It's possible that top-ranked reviewers are being plagiarised by others

### Spam Detection based on Atypical Behaviours

- Lim et al (2010) used data mining with models of atypical behaviour to assign a spam score to reviewers
- Suspect behaviours included
	- Promoting or victimising a few target products
	- Targetting a group of products in a short period of time
	- Tending to always give very high or very low scores
	- Giving ratings which deviate from the rest of the population
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI4NDkwNzQ5MywtODM4MzQ1NzYyLDE3Nz
AxMzMwMTIsMTY0NjA1Miw0NDExMjcwMzEsLTkyNzQ5NTg3Nywx
NzA1NjQyMjIzLC0xNDA1MDA1MDQxLC03MDMzNjk4MzAsMTYwOT
UyNzgzMSw3MzA5OTgxMTZdfQ==
-->