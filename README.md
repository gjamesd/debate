# A quick analysis of the words across time. 

This quick exercise was done without any political party in mind. It was simply done to ask the question, how have the topics, themes, and words of presidential debates changed across time. 

The approrach is fairly straightforward, mostly using rules based tools rather than transformers, we wanted to understand what has changed across time.

Pease see this link for an entire analysis: https://bestideaswin.substack.com/p/has-america-become-smarter-or-dumber?r=k6evd&utm_campaign=post&utm_medium=web&triedRedirect=true

A technical explination is detaield below: 
This quick algorithm uses 4 rules based approaches to garner insights to the changes in debate rhetoric across time. 

Sentiment Analysis (Vader): The function uses Vader (Valence Aware Dictionary and sEntiment Reasoner) to perform sentiment analysis on each debate text. Vader is a lexicon and rule-based model designed for sentiment analysis, especially on social media content. It breaks down the text and assigns a "polarity score" based on positive, neutral, negative, and compound sentiment using predefined word scores and linguistic heuristics. The polarity_scores(x)method returns a dictionary that quantifies the text’s positivity, negativity, neutrality, and overall sentiment. 

Grade Level (Flesch-Kincaid Grade): The function estimates the complexity of the text by applying the Flesch-Kincaid Grade Level formula. This readability test evaluates sentence length and word complexity to calculate how many years of formal education are needed to understand the text. The flesch_kincaid_grade(x) method from the textstat library is applied to each debate transcript, and the calculated grade level is added to the Grade Level column. 

Readability Score (Flesch Reading Ease): The function also computes the Flesch Reading Ease score to assess how easy or difficult the text is for an average reader. This formula evaluates sentence length and syllable count, with higher scores indicating easier readability. The flesch_reading_ease(x) method calculates this score for each text and adds it to the Readability Score column. Like the Flesch-Kincaid Grade Level, this method is formula-based and doesn't involve transformer models or machine learning.

Polarity and Subjectivity Analysis (TextBlob): This function evaluates the sentiment of debate texts using TextBlob, a library that provides simple tools for processing textual data. TextBlob’s sentiment analysis breaks down each text into two main metrics:

* Polarity: This measures how positive or negative a statement is, ranging from -1 (very negative) to +1 (very positive). A score of 0 indicates a neutral sentiment.

* Subjectivity: This assesses how subjective or objective the text is. A score close to 0 implies the text is more objective (fact-based), while a score closer to 1 suggests it is more subjective (opinion-based).
The racing Bar Charts were created by subsetting the data to only include debates that were linked to the General Elections, then excluding stop words, simply counting the most common words in the corpus of each debate. 





