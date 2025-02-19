# Garage Gym Reviews Recommendation System

**Abstract:** 

The home gym equipment industry is expected to grow by 1.5 billion dollars or 17.6% between the year 2020 and 2021. Much of this equipment will be purchased through online relators where customers will not have the chance to see these items in person. Home gym equipment can be very large and heavy, which makes returning some items extremely costly. These facts make equipment reviews more important than ever. Many consumers will look to equipment reviews to compare and contrast products before making a final decision. Thorough research can lead to higher consumer satisfaction and a reduced need to return items. Garage Gym Reviews (GGR) curates a blog that does just that; compares and contrasts many different pieces of equipment for consumers who can otherwise see these items in person. In order to enhance the consumer experience on GGR a recommendation system has been proposed. This recommendation system uses a content based approach and topic modeling to suggest related blogs to the current blog being read. The corpus was broken into 10 distinct topics for recommendations to be made.

**Body:**

Each blog from Garage Gym reviews was scraped using BeautifulSoup. A total of 432 blog posts were found, with an average length of 1,600 words. The data collected was blog title, body text, and blog url. After data collection, there were over 19,000 unique terms. Cleaning needed to be done to make the data more manageable. Data was first tokenized on white space and punctuation. Next, stop words were removed, numbers and punctuation were removed, and extra white spaces were removed. Lemmatization was used to group together different inflections of words to be analyzed as a single item. The last major step to reduce the number of terms was done with the term frequency inverse document frequency (Tfidf) vectorizer. A threshold was set that removed terms that appeared in more that 60% of the documents and fewer than 1% of the documents. The Tfidf vectorizer converted the corpus into a sparse document-term matrix. This cleaning process reduced the number of terms from 19,000 down to less than 6,000 terms. 

The non-negative matrix factorization (NMF) method was used to reduce the dimensionality of the document-term matrix even further. The NMF method was set to parse the document term matrix into 10 topics. This in turn made a document-topic matrix and a topic-term matrix. The document-topic matrix gave each document a weight for each of the 10 topics. The document with the highest weight in a specific topic would be the most heavily correlated to that topic. The topic-term matrix gives each term a specific weight in each topic. This matrix decomposition allows for much faster processing of a larger dataset to take place. 

From the 10 topics, the terms with the highest weight could be extracted. These terms gave a description of how the topic was formulated. For instance topic 1 in the analysis contained the words: shoe, nike, metcon, heel, nano, and reebok. All of these terms are weightlifting shoe related. When using the document-topic matrix you can find that the document most heavily correlated to topic 1 is called, “7 Best CrossFit Shoes of 2021”. This reinforces the assumption that topic 1 is related to weightlifting shoes. 

## Topic Modeling Output

![](../Images/GGR_10_Topics.png)

**Topic Analysis:**

**Topic 0:** Rack and rack accessories

**Topic 1:** Weightlifting shoes

**Topic 2:** Barbells

**Topic 3:** Cardio bikes

**Topic 4:** Adjustable dumbbells

**Topic 5:** Cardio machines

**Topic 6:** Weightlifting belts/ belt squat machine

**Topic 7:** Weight plates

**Topic 8:** Loadable weight vests

**Topic 9:** Weight benches
