Strava Review Text Mining Analysis
Topic modeling of English-language Strava user reviews from the Google Play Store.

Final project for Text Mining at Dongguk University, by Lawand Abbas.
Overview
The project scrapes public reviews of the Strava app, cleans and lemmatizes them, and applies Latent Dirichlet Allocation (LDA) to uncover the main themes users write about. The optimal number of topics was selected by maximizing the c_v coherence score across 5–20 topics, which yielded 7 topics.
Pipeline
Scraping — collect all English/US reviews for com.strava via google-play-scraper
Cleaning — lowercase, strip URLs, digits, punctuation and extra whitespace
POS filtering — keep nouns, adjectives and content verbs as lemmas (spaCy en_core_web_sm); drop high-frequency light verbs
Vectorization — build a gensim Dictionary and bag-of-words corpus, filtering extreme terms (no_below=20, no_above=0.9)
Model selection — train LDA for 5–20 topics and compare c_v coherence
Final model — LDA with 7 topics
Interpretation — pyLDAvis visualization, top 20 keywords per topic, and the most representative review per topic
Files
File
Description
Lawand_Abbas_TextMining_FinalProject.ipynb
Full analysis notebook
Lawand_Abbas_TextMining_FinalProject.pdf
Written report

Requirements
google-play-scraper

spacy  +  en_core_web_sm

gensim==4.3.1

numpy==1.23.5

scipy==1.10.1

pyLDAvis

pandas

matplotlib
