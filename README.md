## Overview of the Dataset
  - Number of Rows: 953
  - Number of Columns: 24
  - Datatypes on each column:
     - **Object:** track name, artist(s) name, streams, in Spotify playlists, in Apple playlists, in Deezer playlists, in Shazam charts, key, mode
     - **Int64:** artist count, released year, released month, released day, in Spotify charts, in Apple charts, in Deezer charts, bpm, danceability, valence, energy, acousticness, instrumentalness, liveness, speechiness

## Basic Descriptive Statistics
  - Mean: 514137424.93907565
  - Median: 290530915.0
  - Standard Deviation: 566856949.0388832

### Distribution of Release Year:
![image](https://github.com/user-attachments/assets/5ba30fb0-df94-428b-bf9d-4c956df5844f)
### Distribution of Artist Count:
![image](https://github.com/user-attachments/assets/48026347-8d48-498e-9abb-7502feb00ab8)
- **Answer:** The graph for the released_year is skewed towards the right, indicating that the number of released tracks increases as the years go by. The artist_count is skewed to the left, indicating that the number of artists in most tracks in the given dataset consists of only one artist.
## Top Performers
### Top 5 Tracks:
![image](https://github.com/user-attachments/assets/6576b7ca-9471-4d26-9857-cc1b166d48d3)
- **Answer:** The image above is the Top 5 most streamed tracks. The highest-streamed track is "Blinding Light" by The Weeknd.
## Temporal Trends
#### The Tracks Released Per Year:
![image](https://github.com/user-attachments/assets/c2913f62-49cd-4abd-8636-17f4da4b6164)
#### The Number of Tracks Released Every Month:
![image](https://github.com/user-attachments/assets/c11b01c8-ecf0-49fb-b423-cde3c496b607)
- **Answer:** From what I noticed in the graph, the trend of tracks released per year is that the number of streams gradually increases as the years go by. The graph for the released_year is skewed towards the right, indicating that the number of released tracks increases as the years go by. The artist_count is skewed to the left, indicating that the number of artists in most tracks in the given dataset consists of only one artist.
## Genre and Music Characteristics
### Correlation of BPM and Streams(in Billions)
![image](https://github.com/user-attachments/assets/84e307d7-3c25-4d4d-9829-f2a2ca50192f)
  - **Answer:** Based on my understanding of the graph, the correlation between the BPM and Streams is weak since the scatter plot is too scattered apart to indicate a reliable correlation
### Correlation of Danceability and Streams(in Billions)
![image](https://github.com/user-attachments/assets/bdfc361c-83a9-47d6-931b-06b530b40bfb)
  - **Answer:** The density of this scatter plot is less scattered than the bpm and streams scatter plot.
### Correlation of Energy and Streams(in Billions)
![image](https://github.com/user-attachments/assets/4692fe89-d36f-4491-bcab-2c0431a91ac0)
  - **Answer:** This scatter plot has a denser scatter plot compared to the two previous plots 
### Which attributes seem to influence streams the most?
  - **Answer:** Based on the data given to me, the attribute that influences the streams the most is energy since it correlates strongly with streams compared to the correlation of danceability and BPM to streams.
### Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?
![image](https://github.com/user-attachments/assets/eb581935-6fd9-445c-9500-1e92cd3ba4a9)
![image](https://github.com/user-attachments/assets/54121e1a-649a-40c4-bb63-62abecc0abc3)
  - **Answer:** Based on my observation, I noticed that the correlation between danceability and energy is stronger than the correlation between valence and acousticness because the plots in the correlation of valence and acousticness are more scattered compared to the correlation between danceability and energy.

## Platform Popularity
![image](https://github.com/user-attachments/assets/fd1893ac-6723-477c-a515-4dba893d35df)
  - **Answer:** Observing the graph, I saw that the Spotify playlist dominated the graph and was more favored than the two variables.
![image](https://github.com/user-attachments/assets/38ae68b1-8104-49b5-b98e-67a62e4baaa8)
  - **Answer:** Using the data from the "Top Performers," I saw that Spotify playlist is the top track's favored platform.

## Advanced Analysis
### The Graphs for the top 20 tracks with the same keys:
#### A key:
![image](https://github.com/user-attachments/assets/4014d665-28c6-4087-ae4d-e68e7c03ba0d)
#### A# key:
![image](https://github.com/user-attachments/assets/49cf1ef0-ecf4-48eb-bec5-139a3bff4941)
#### B key:
![image](https://github.com/user-attachments/assets/3e5a9bba-0b57-4f9e-8fcf-923e27fcaf88)
#### C# Key:
![image](https://github.com/user-attachments/assets/613ca438-67eb-46ba-a666-6f850cc66da1)
#### D key:
![image](https://github.com/user-attachments/assets/161dbd1a-8942-4efe-8897-7b8c74dab786)
#### D# key:
![image](https://github.com/user-attachments/assets/6d81c5e1-7c32-4475-ac2c-9ebfe9ce028e)
#### E key:
![image](https://github.com/user-attachments/assets/3ef27f8d-bea8-4e2f-ad6e-3e68b800aca4)
#### F key:
![image](https://github.com/user-attachments/assets/79fff8a7-cb43-436e-874e-323272fb0839)
#### F# key:
![image](https://github.com/user-attachments/assets/4f9058b4-8050-43bb-ae3d-7bb044667693)
#### G key:
![image](https://github.com/user-attachments/assets/223da2f5-1303-4d77-8a17-bd70c3e343de)
#### G# key:
![image](https://github.com/user-attachments/assets/45712e1c-da33-42a0-bb97-cfebe5b84d53)
### The Average of each track with the same keys:
![image](https://github.com/user-attachments/assets/31c0c3a8-7a72-440e-b161-59b9cf0deca5)
**Answer:** Based on my observations of each track with the same key, I only saw the pattern go downward, showing this graph is ranked from the highest streamed track to the lowest streamed track. If using this, it is reliable to see which track with the same key has the highest streams or what the top number-performing track with the same key will be.
### Graph of the Average streams comparing Major and Minor Mode:
![image](https://github.com/user-attachments/assets/47e7cb39-48fa-4ed4-bf89-fc160a83f8e0)
**Answer:** Based on the graph, the listeners favor the Major mode more than the Minor Mode.

## Documentation

### October 21, 2024
#### Overview of the Dataset
  - When loading the CSV file, it is having a UnicodeDecodeError so I found a way to resolve it by using "encode = 'latin1'" [^1] 
  - Realizing that the data type for the 'streams' column is wrong, I used `.astype(float)` on the 'streams' column to convert the datatype from Object to Float. The code snippet is:
     ```
     spot_data['streams'] = pd.to_numeric(Spot_Data['streams'], errors = 'coerce')
     spot_data.dtypes
     ```
     #### Output before conversion:
          streams                 object
     #### Output after conversion:
          streams                 float64

### October 22, 2024
#### Overview of the Dataset:
  - When I reran the code, it showed an error that said "ValueError." What I did was change the code from `.astype(float)` to `pd.to_numeric(Spot_Data['streams'], errors = 'coerce')`, and it worked.[^2]
  - `pd.to_numeric()` converts it from object to float because when I looked at the raw data, it is in exponential form, and casting to integers would have caused an int casting error.
  - The code snippet is:
    ```
    spot_data['streams'] = pd.to_numeric(Spot_Data['streams'], errors = 'coerce') #Convert the Data from Object to Float.
    spot_data['streams'].dtypes
    ```
    #### Output before the conversion:
        dtype('O')
    #### Output after the conversion:
        dtype('float64')

#### Basic Descriptive Statistics:
  - After converting the 'streams' column from Object to Float, it was time to calculate the mean, median, and standard deviation:
    ```
    # Find the Mean
    data_mean = spot_data['streams'].mean()
    print("Mean:", data_mean)

    # Find the Median
    data_mid = spot_data['streams'].median()
    print("Median:", data_mid)

    # Find the Standard Deviation
    data_std = spot_data['streams'].std()
    print("Standard Deviation:", data_std)
    ```

    #### Outputs:
    ![image](https://github.com/user-attachments/assets/928991e8-c9e6-4a7e-a855-6b668bdfa54a)

  - Then, I looked for the frequencies of the data for the Artist Count and Release Year using the code:
    ```
    freq_release = spot_data['released_year'].value_counts() #Find the Frequency for Each year.
    freq_release

    freq_artist = spot_data['artist_count'].value_counts() # Generate the Data for the Artist count
    freq_artist
    ```

  - Used `histplot` to display the distributions for the Artist Count and Release Year as graphs using Seaborn.

    #### Generate the Release Year Histogram:
    ```
    sns.histplot(spot_data['released_year'], color='orange') # Generate the histogram using Seaborn
    # Use matplot to modify the graph and show the graph
    plt.title('Distribution of Released Year')
    plt.xlabel('Released Year')
    plt.ylabel('Frequency')
    plt.show()
    ```

    #### Generate the Artist Count Histogram:
    ```
    sns.histplot(spot_data['artist_count'], color='green') # Generate the histogram using Seaborn
    # Use matplot to modify the graph and show the graph
    plt.title('Count of Artist Count')
    plt.xlabel('Artist Count')
    plt.ylabel('Frequency')
    plt.show()
    ```

### October 23, 2024
#### Basic Descriptive Statistics
  - I noticed that the graph for the Released Year was too small and hard to read. I found a solution to make it more readable by adjusting the number of bins:[^3]
    ```
    sns.histplot(spot_data['released_year'], color='orange', bins = 50) # Generate the histogram using Seaborn
    # Use matplot to modify the graph and show the graph
    plt.title('Distribution of Released Year')
    plt.xlabel('Released Year')
    plt.ylabel('Frequency')
    plt.show()
    ```
    #### The previous graph for the Released Year:
    ![image](https://github.com/user-attachments/assets/51619a33-fe38-4910-bf95-20380b20e5b5)

#### Top Performaers:
  - When sorting the values of streams, I found out that the last value was "NaN," and when ranking, the output looked like this:
    ```
    top_five = spot_data['streams'].sort_values().tail(6).iloc[::-1].reset_index()
    top_five
    ```
    ![image](https://github.com/user-attachments/assets/3e77a762-6453-414e-9d0c-2a8ad312e768)

  - I assumed that "NaN" was not counted, so I used `.dropna()`[^4] to exclude it:
    ```
    top_five = spot_data['streams'].sort_values().tail(6).iloc[::-1].reset_index()
    top_five.dropna()
    ```
    ![image](https://github.com/user-attachments/assets/7e1d177a-63da-40a4-b2c7-f9f021b33b5a)

### October 24, 2024
#### Basic Descriptive Statistics
  - In the basic descriptive statistics section, I updated the graph by adding a Kernel Density Estimate (KDE) and a grid for readability. The new code is:[^3]
    ```
    sns.histplot(spot_data['released_year'], color='orange', bins = 50, kde = True) # Generate the histogram for the released year using Seaborn
    sns.histplot(spot_data['artist_count'], color='green', kde = True) # Generate the histogram for the artist count using Seaborn
    ```
#### Top Performers
  - I forgot to include the track name in the Top Performers section, so I rewrote the code to include both streams and track names. Here is the new code:
    ```
    top_five_streams = spot_data.sort_values(by = 'streams').tail(6).iloc[::-1].reset_index()
    # Sorting the column 'streams' and assuming "NaN" is not counted
    # Putting the tail in descending order then resetting the index before removing the "NaN"
    print(top_five_streams[['track_name', 'streams']].dropna())
    ```
#### Temporal Trends:
  - This part is almost the same as the basic descriptive statistics, where I will look for the graph of the tracks released per year and compare the tracks released every month
```
release_data = spot_data.groupby('released_year').size().reset_index(name='track_count') #check the ff. data and output it
release_data


sns.histplot(x='released_year', data = release_data, color='red', kde = True)#Generate a Line graph with the month on the x-axis
#number of tracks in the y-axis
plt.title('Tracks Released Per Year')#title of the graph
plt.xlabel('Release Year')#label in the x-axis
plt.ylabel('Number of Tracks')#label in the y-axis
plt.grid(True) #add a grid
plt.show() #print the graph

month_of_release = spot_data.groupby('released_month').size().reset_index(name='track_count') #check the ff. data and output it
month_of_release


sns.lineplot(x='released_month',y='track_count', data = month_of_release, color='brown', marker = 'o') #Generate a Line graph with the month on the x-axis
#number of tracks in the y-axis
plt.title('Number of Tracks Every Month') #title of the graph
plt.xlabel('Month') #label in the x-axis
plt.ylabel('Number of Tracks Released') #label in the y-axis
plt.grid(True) #add a grid
plt.show() #print the graph
```
### October 25, 2024
#### Genre and Music Characteristics
  - First, I coded for the graph, looking for the correlation between BPM and Streams.
```
stream_and_bpm = spot_data[['bpm', 'streams']] #look for the values of BPM and Streams
stream_and_bpm.dropna() #print for checking

plt.figure(figsize=(20,10))#Adjust the size of the graph
sns.scatterplot(x='bpm',y='streams', data = stream_and_bpm, color='black', marker = 'o') #Generate a Line graph with the month on the x-axis
#number of tracks in the y-axis
plt.title('Relationship Of The Number of Streamsa and BPM') #title of the graph
plt.xlabel('BPM') #label in the x-axis
plt.ylabel('streams In Billions') #label in the y-axis
plt.grid(True) #add a grid
plt.show() #print the graph
```
  - I realized when coding for the correlation of streams and danceability and energy that I could use the main dataframe to call the data instead of creating a separate line of code specifically calling the two columns I needed. I used the same code from my previous code in the "Number of Tracks Released Every Month" since I was using the same type of graph, but I realized that I did not need to group the values.[^5]
  - Another mistake on my part is that I used the wrong plot to see the correlation between the two variables. I should've used a scatter plot instead of a line plot.
  - The code for danceability and stream graph
```
plt.figure(figsize=(20,10))#Adjust the size of the graph
sns.scattereplot(x='danceability_%',y='streams', data = spot_data, color='maroon', marker = 'o') #Generate a Line graph with the month on the x-axis
#number of tracks in the y-axis
plt.title('Relationship Of The Number of Streams and Danceability') #title of the graph
plt.xlabel('Danceability') #label in the x-axis
plt.ylabel('Streams In Billions') #label in the y-axis
plt.grid(True) #add a grid
plt.show() #print the graph
```
  - The code for the energy and streams graph
```
plt.figure(figsize=(20,10))#Adjust the size of the graph
sns.scatterplot(x='energy_%',y='streams', data = spot_data, color='purple', marker = 'o') #Generate a Line graph with the month on the x-axis
#number of tracks in the y-axis
plt.title('Relationship Of The Number of Streams and Enery') #title of the graph
plt.xlabel('Energy') #label in the x-axis
plt.ylabel('Streams In Billions') #label in the y-axis
plt.grid(True) #add a grid
plt.show() #print the graph
```
### October 26, 2024
#### Genre and Music Characteristics
  - I started doing the Correlation of Danceability and Energy, and Valence and Acousticness
  - The Code for the Danceabilit and Energy
```
plt.figure(figsize=(20,10))#Adjust the size of the graph
sns.scatterplot(x='energy_%',y='danceability_%', data = spot_data, marker = 'o') #Generate a Line graph with the month on the x-axis
#number of tracks in the y-axis
plt.title('Relationship Of Energy and Danceability') #title of the graph
plt.xlabel('Energy') #label in the x-axis
plt.ylabel('Danceability') #label in the y-axis
plt.grid(True) #add a grid
plt.show() #print the graph
```
  - The code for the Valence and Acousticness
```
plt.figure(figsize=(20,10))#Adjust the size of the graph
sns.scatterplot(x='valence_%',y='acousticness_%', data = spot_data, color = 'green', marker = 'o') #Generate a Line graph with the month on the x-axis
#number of tracks in the y-axis
plt.title('Relationship Of Valence and Acousticness') #title of the graph
plt.xlabel('Valence') #label in the x-axis
plt.ylabel('Acousticness') #label in the y-axis
plt.grid(True) #add a grid
plt.show() #print the graph
```
---
### Platform Popularity
  - I start finding the sums of the following platforms for comparison. After finding the means, I plan on turning them into a Dictionary and a DataFrame. I first tried to make the same approach when reviewing the "Pandas.ipynb" but Realized that I need the keys and values to be in a row, not the keys and values to be in a column. So, looking around the internet, I found that using .items() would make the rows and values be in a column, and this allowed me to create a different name for the Columns, then went to graphing the DataFrame.[^6]
  - As a side note, I divided the sums to 1e6 to remove it from the graph since it is already mentioned that it is in millions.
```
#Find the sums of each platform divided into 1e6 for simplification
spotify_playlist_count = spot_data['in_spotify_playlists'].sum()
spotify_chart_count = spot_data['in_spotify_charts'].sum()
apple_playlist_count = spot_data['in_apple_playlists'].sum()
#Turn this into a Dictionary
norm_data = {'Spotify Playlist' : spotify_playlist_count, 'Spotify Chart' : spotify_chart_count, 'Apple Playlist' : apple_playlist_count}
#Convert the Dictionary to a DataFrame
graph_data = pd.DataFrame(norm_data.items(), columns=['platform', 'tracks'])
#Generate the Graph for comparison
sns.barplot(x = 'platform', y = 'tracks', data = graph_data, color='maroon')
plt.title('Comparing the Number of Total Tracks Based in the Platforms')
plt.xlabel('Platforms')
plt.ylabel('Tracks (in Millions)')
plt.show()
```
  - looking for the favored platform used by the top-performing tracks, I used the previous code in "Top Performers" as my basis for analyzing the favored platform by the top tracks.
```
x = top_five_streams[['in_spotify_playlists']].sum()
y = top_five_streams[['in_spotify_charts']].sum()
z = top_five_streams[['in_apple_playlists']].sum()
print("The sum of the Top performing Tracks that favors using the Spotify Playlist is ", x)
print("The sum of the Top performing Tracks that favors using the Spotify Chart is ", y)
print("The sum of the Top performing Tracks that favors using the Apple Playlist is ", z)
```

## October 28, 2024
#### Platform Popularity
  - So, using the .sum() is not that reliable since I am looking for the average track count in the Spotify playlist, Spotify charts, and Apple playlist. So I changed it from .add() to .mean().
  - The adjustments made in the code:
```
spotify_playlist_count = spot_data['in_spotify_playlists'].mean()
spotify_chart_count = spot_data['in_spotify_charts'].mean()
apple_playlist_count = spot_data['in_apple_playlists'].mean()
#Turn this into a Dictionary
norm_data = {'Spotify Playlist' : spotify_playlist_count, 'Spotify Chart' : spotify_chart_count, 'Apple Playlist' : apple_playlist_count}
#Convert the Dictionary to a DataFrame
graph_data = pd.DataFrame(norm_data.items(), columns=['platform', 'tracks'])
#Generate the Graph for comparison
sns.barplot(x = 'platform', y = 'tracks', data = graph_data, color='maroon')
plt.title('Comparing the Number of Total Tracks Based in the Platforms')
plt.xlabel('Platforms')
plt.ylabel('Tracks (in Millions)')
plt.show()

x = top_five_streams[['in_spotify_playlists']].mean() #Use the Top performer's value to sum the number of tracks in the playlist
y = top_five_streams[['in_spotify_charts']].mean()
z = top_five_streams[['in_apple_playlists']].mean()
print("The mean of the Top performing Tracks that favors using the Spotify Playlist is ", x)
print("The mean of the Top performing Tracks that favors using the Spotify Chart is ", y)
print("The mean of the Top performing Tracks that favors using the Apple Playlist is ", z)
```
#### Advanced Analysis 
  - For creating a graph of the mean for each key, I first loaded up the data
```
#find the means for each key
key_data = spot_data.groupby('key')['streams'].mean()
#Print the Means
print ('The average on each key is: ', key_data)
```
  - Then, I converted it to the dictionary. At first, I thought of using the same method I used before, where I made the dictionary manually but came up with a Value Error, so I looked at some sources to resolve this issue and found the .to_dict().[^7]
```
key_dict_data = key_data.to_dict()
```
  - After that, I did the same thing: I converted the Dictionary into a DataFrame and then created the graph.
```
#convert Dictionary to DataFrame
key_graph_data= pd.DataFrame(key_dict_data.items(), columns=['key', 'streams'])
#Create the graph
sns.barplot(x = 'key', y = 'streams', data = key_graph_data, color = 'green')
plt.title('Comparing the Mean of Each Key')
plt.xlabel('Key')
plt.ylabel('Streams')
plt.show()
```
## October 29, 2024
### Advanced Analysis
  - So, I realized that I needed to compare the number of streams of the tracks with a similar key.
  - **Note: I will use the same code for all of the keys, so for clarity, I will enclose the changed variables with a parenthesis ().**
  - I learned that you can set it as ascending = False so it will go in descending order.[^8]
```
#Sort the spot_data by streams
keys = spot_data.sort_values(by = 'streams', ascending = False)
#Call the specific data needed
(key value)_key_data = keys.loc[(spot_data['key'] == '(key value)')].head()
#Plot the graph
plt.figure(figsize = (15, 10))
sns.lineplot(x ='track_name', y ='streams', data = (key value)_key_data, color ='(color)', marker ='o')
plt.title('Tracks with the Same Key') #Title
plt.xlabel('Track')  #Label for track names
plt.ylabel('Streams')  #Label for stream counts
plt.grid(True)
plt.show()
```
## October 30, 2024
### Advance Analysis
  - A couple of changes in the code: I will now use the top 20 instead of the top 5 Highest streams to make the analysis more accurate. When I got the overlapping problem, I looked for a solution and found one in the Stackoverflow.[^9] But it showed a user error, and I looked for a solution and found .xticks().[^10]
```
#Sort the spot_data by streams in descending order
keys = spot_data.sort_values(by = 'streams', ascending = False)
#Call the specific data needed
(key)_key_data = keys.loc[(spot_data['key'] == '(key)')].head(20)
#Plot the graph
plt.figure(figsize = (20, 10))
sns.lineplot(x = 'track_name', y = 'streams', data = (key)_key_data, color ='(color)', marker ='o')
plt.title('Tracks with the Same Key') #Title
plt.xlabel('Top 10 Tracks with the Key (key)')  #Label for track names
plt.ylabel('Streams')  #Label for stream counts
plt.grid(True)
plt.xticks(rotation=40, ha='right')
plt.show()
```
## Libraries Utilized
  - Pandas
  - Matplotlib.pyplot
  - Seaborn

## Authors
  - Kyle Nathaniel V. Dimalanta

## Version History
## 0.8 - October 29, 2024
  - Some Additions in Advanced Analysis
### 0.7 - October 28, 2024
  - Start creating the Advance Analysis
  - Fix Platform Popularity from .sum() to .mean()
### 0.6 - October 26, 2024
  - Added the references to the documentation
  - Start creating the Platform Popularity
### 0.5 - October 25, 2024
  - Using a different plot from line plot to scatter for the correlations
  - Some adjustments to the structure of grammar.
  - Started creating the Genre and Music Characteristics
### 0.4 - October 24, 2024
  - Minor adjustment to the name of the graph.
  - Started creating the Temporal Trends
  - Changed the code for the Top 5 performers since the track name and artist was missing
  - Added KDE to the graphs for better presentation

### 0.3 - October 23, 2024
  - Created the Data Analysis for the "Top Performers"
  - Adjusted the histogram for the Released Year to make it more readable

### 0.2 - October 22, 2024
  - Added matplotlib and Seaborn Libraries
  - Fixed the ValueError when converting the 'streams' column from Object to Float

### 0.1 - October 21, 2024
  - Calculated the Mean, Median, and Standard Deviation of the 'streams' column
  - Created the Data Analysis for the "Overview of Dataset"
  - Fixed the data type of 'streams' to Float instead of Object
  - Fixed the encoding parameter to 'latin1' due to 'UTF-8' errors
  - Loaded the CSV file

## References:
[^10]: https://matplotlib.org/stable/api/_as_gen/matplotlib.axes.Axes.set_xticklabels.html
[^9]: https://stackoverflow.com/a/42674281/23541370
[^8]: https://blog.hubspot.com/website/pandas-sortby#:~:text=Pandas%20Sort%20by%20Column&text=Sorting%20data%20within%20a%20dataframe,the%20values%20in%20descending%20order.
[^7]: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_dict.html
[^6]: https://stackoverflow.com/a/18837389/23541370
[^5]: https://www.westga.edu/academics/research/vrc/assets/docs/scatterplots_and_correlation_notes.pdf
[^4]: https://saturncloud.io/blog/python-pandas-how-to-remove-nan-and-inf-values/
[^3]: https://seaborn.pydata.org/generated/seaborn.histplot.html
[^2]: https://stackoverflow.com/questions/15891038/change-column-type-in-pandas/28648923#28648923
[^1]: https://stackoverflow.com/a/53361168/23541370
