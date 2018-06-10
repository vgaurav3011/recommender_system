Today we are going to walk through building a basic recommender system which, when given a music artist, will recommend similar artists. The dataset, obtained from LastFM in 2011, contains the play counts of 17,632 artists by 1,892 users, is available at [GroupLens](https://grouplens.org/datasets/hetrec-2011/) on behalf of [Lab41](https://github.com/Lab41/hermes/wiki/Datasets).

There are two main types of recommender system: **content-based**, and **collaborative**. Content-based recommends based on past browsing history of similar items to provide recommendations, whereas collaborative takes data from similar users to provide recommendations.

Last.fm uses the collaborative method to provide music recommendations to its users.  This is in contrast to a service such as Pandora which provides content recommendations based features such as similarity within the audio file patterns themselves.   

Our basic recommender will be a collaborative recommender system, where we essentially build a sparse matrix comparing artist plays (rows) by user (columns). This data will then be passed through a latent mapping algorithm, such as K-nearest neighbors, to determine cosine similarity amongst the user/artist relationships.  This will help us determine which artists are most similar.  For instance, when a user plays the Beatles, they also have a high probability of playing the Rolling Stones.   

**The Dataset**

Key features include:
- userID
- friendID
- artistID, Name
- weight (plays by user of artist)
- tagID, tagValue

Temporal:
- timestamp
- day, month, year

**Questions to ponder**

Ask yourself why would they have selected this problem for the challenge? What are some gotchas in this domain I should know about?

What is the highest level of accuracy that others have achieved with this dataset or similar problems / datasets ?

What types of visualizations will help me grasp the nature of the problem / data?
What feature engineering might help improve the signal?

Which modeling techniques are good at capturing the types of relationships I see in this data?

Now that I have a model, how can I be sure that I didn't introduce a bug in the code? If results are too good to be true, they probably are!

What are some of the weaknesses of the model and and how can the model be improved with additional work?
