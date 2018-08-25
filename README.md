# Cards Against Humanity  CAHBot 

*An AI designed for you to play alone* | *Warning: Contains explicit content not suitable for children under 18*

*By: Belle Peng*  |  *2018 August*

**<u>Project Goals:</u>**

**Joke Generator** - Given a randomly chosen question pick funny answers

**Topic Modeling & Clustering** - Find CAH’s favorite subjects and words on the Answer Cards

**Generate new Answer Cards (Natural Language Generation NLG)** - Because the old cards are now tired if you play the game enough times

<br><br/>

<u>**Methods Used and Results:**</u>

**Joke Generator**

Methods / Tools Used: Word2Vec & Cosine Similarity

Results: For every question card, see the funny answer outputs in *results/CAH Predicted Answers.pdf*. The generated pairs are then used as the "labeled data" for the NLG portion, saved as *data/CAH_predicted_answers.txt*.

**Topic Modeling** / **Clustering**

Methods / Tools Used: Non-Negative Matrix Factorization (NMF) with Count Vectorizer, Latent Semantic Analysis (LSA) with TFIDF Vectorizer, K-Nearest Neighbor, DBScan, Inertia, Silhouette Score

Results: 6 Topics with word weights, which I then manually give them sensible names. The words associated with the topics are shown in the presentation slides. I also found 6 clusters are distinct, however the main cluster contains 90% of the cards don't seem to have any clustering structure. 

**Generate new Answer Cards (NLG)** 

Methods / Tools Used: Recurring Neural Network (RNN)

Results: Generated word-by-word as well as character-by-character answers for a given question.



*Data:*

The starting dataset for this analysis is *data/cah.json*. The *data/CAH_predicted_answers.txt* is a generated dataset for the NLG portion. *data/model_nlg_1.pt* and *data/model_nlg_2.pt* are the final trained model from the NLG portion. Due to the long training time, these models are saved to be run easily without having to re-run. The results are presented and summarized in *results/CAH Deck.pptx*