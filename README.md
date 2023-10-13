Song Recommender<b><br>
Description:<br>
The recommender.ipynb script is designed to provide song recommendations based on user input and historical data. Utilizing advanced algorithms, it ensures accurate and relevant song suggestions.<br>
<br>
Requirements:<br>
Python 3.x<br>
pandas<br>
numpy<br>
spotipy (for Spotify API integration)<br>
<br>
<br>
How to Run:<b><be>
Ensure you have all the required libraries installed.<br>
Navigate to the directory containing the recommender.ipynb script.<br>
Run the command: python recommender.ipynb<br>
<br>
<br>
Features:<b><br>
User-based recommendation<br>
Item-based recommendation<br>
Hybrid recommendation approach<br>
Spotify API integration for fetching song URLs<br>
<br>
<br>
Data Preparation:<b><br>
The script reads two datasets, hot and not_hot, which contain information about songs, including their features.<br>
An extra id column that's not needed is dropped.<br>
A 'hot' column is added to both datasets to label whether each song is hot ('Yes' for hot songs and 'No' for not hot songs).<br>
The 'hot' and 'not hot' datasets are concatenated into a single dataframe named all_songs, combining both sets of songs for clustering.<br>
Data is scaled to have a mean of 0 and a standard deviation of 1 using StandardScaler. The scaling parameters are saved for later use.<br>
<br>
<br>
K-Means Clustering:<b><br>
K-Means clustering is performed on the scaled data for different values of k.<br>
The inertia and silhouette score for each k are calculated to determine the optimal number of clusters. The optimal value appears to be k=3 based on the silhouette score.<br>
Songs are assigned to their respective clusters, and a 'clusters' column is added to the all_songs dataframe.<br>
<br>
<br>
Spotify API Integration:<b><br>
The script integrates with the Spotify API using the spotipy library.<br>
Functions are defined to fetch the Spotify URL for a given song and artist and to recommend a song based on user input.<br>
<br>
<br>
User Interaction & Recommendation:<b><br>
The user is prompted to input their favorite song and artist.<br>
Based on the user's input and cluster information, the script retrieves the Spotify URL and other details for a recommended song.<br>
The recommendation logic checks if the user's favorite song is in the 'hot' dataset. If it is, a song from 'hot' songs in the same cluster is recommended. Otherwise, a song from 'not hot' songs in the same cluster is suggested.<br>
The recommended song title and its Spotify URL are displayed.<br>
<br>
<br>
Exporting Data:<b><br>
The dataframe with cluster information is exported to a CSV file named 'all_songs_clustered.csv'.<br>

Author:<b><br>
Faryal, Chibudem, Rodrigo
