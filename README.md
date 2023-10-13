Song Recommender<b>
Description:<b>
The recommender.ipynb script is designed to provide song recommendations based on user input and historical data. Utilizing advanced algorithms, it ensures accurate and relevant song suggestions.<b>
<b>
Requirements:<b>
Python 3.x<b>
pandas<b>
numpy<b>
spotipy (for Spotify API integration)<b>
<b>
<b>
How to Run:<b>
Ensure you have all the required libraries installed.<b>
Navigate to the directory containing the recommender.ipynb script.<b>
Run the command: python recommender.ipynb<b>
<b>
<b>
Features:<b>
User-based recommendation<b>
Item-based recommendation<b>
Hybrid recommendation approach<b>
Spotify API integration for fetching song URLs<b>
<b>
<b>
Data Preparation:<b>
The script reads two datasets, hot and not_hot, which contain information about songs, including their features.<b>
An extra id column that's not needed is dropped.<b>
A 'hot' column is added to both datasets to label whether each song is hot ('Yes' for hot songs and 'No' for not hot songs).<b>
The 'hot' and 'not hot' datasets are concatenated into a single dataframe named all_songs, combining both sets of songs for clustering.<b>
Data is scaled to have a mean of 0 and a standard deviation of 1 using StandardScaler. The scaling parameters are saved for later use.<b>
<b>
<b>
K-Means Clustering:<b>
K-Means clustering is performed on the scaled data for different values of k.<b>
The inertia and silhouette score for each k are calculated to determine the optimal number of clusters. The optimal value appears to be k=3 based on the silhouette score.<b>
Songs are assigned to their respective clusters, and a 'clusters' column is added to the all_songs dataframe.<b>
<b>
<b>
Spotify API Integration:<b>
The script integrates with the Spotify API using the spotipy library.<b>
Functions are defined to fetch the Spotify URL for a given song and artist and to recommend a song based on user input.<b>
<b>
<b>
User Interaction & Recommendation:<b>
The user is prompted to input their favorite song and artist.<b>
Based on the user's input and cluster information, the script retrieves the Spotify URL and other details for a recommended song.<b>
The recommendation logic checks if the user's favorite song is in the 'hot' dataset. If it is, a song from 'hot' songs in the same cluster is recommended. Otherwise, a song from 'not hot' songs in the same cluster is suggested.<b>
The recommended song title and its Spotify URL are displayed.<b>
<b>
<b>
Exporting Data:<b>
The dataframe with cluster information is exported to a CSV file named 'all_songs_clustered.csv'.<b>

Author:<b>
Faryal, Chibudem, Rodrigo
