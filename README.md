# music-recommender-system-using-knime-and-knn-algorithm
Find songs similar to your selected song using KNN similarity.

this was a group project 

Person 4 — Recommendation Evaluation
Person 4 took the recommendation outputs for K = 3, 5, 7, 9 and 11 and evaluated them.
Combined the recommendation results with the music data using Joiner nodes. 
Used a Rule Engine to create relevant_flag based on the liked value.
Used GroupBy to calculate:
Sum(relevant_flag) → number of relevant recommendations
Mean(distance) → average recommendation distance
Combined the five K results using Concatenate.
Created a separate diversity-analysis branch using the nine audio features:
 tempo, energy, danceability, acousticness, instrumentalness, liveness, valence, loudness, speechiness.
Calculated standard deviation and then an average for the diversity analysis.
Combined the diversity results for the different K values.

How Mean Distance Helps Find Similar Songs
For each recommended song, the KNN system calculates a distance between the reference song and the other songs using their audio features such as energy, danceability, tempo, and valence.
A smaller distance means the songs are more similar based on those features.
K is the number of nearest songs we want the KNN system to consider as recommendations. So when K = 3, the system finds the three songs with the smallest distance from the reference song. 
Distance tells us how similar two songs are based on their audio features. Smaller distance means more similar.
Then why test K = 3, 5, 7, 9, 11?
Because we want to see how many nearest songs should be considered.
K = 3: only the 3 closest songs
K = 5: the 5 closest songs
K = 7: the 7 closest songs
and so on.
As K increases, we include more songs, but the additional songs can be farther away.
That is why you may see mean distance change.
Recommendation System:  prototype
