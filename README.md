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

## Top Performers
  - The Top 1 track is *Blinding Lights* by The Weeknd with a stream count of 3.703895e+09

### Top 5 Tracks:
![image](https://github.com/user-attachments/assets/6576b7ca-9471-4d26-9857-cc1b166d48d3)

## Temporal Trends
  - From what I noticed in the graph, the trend of tracks released per year is that as the years go by, the number of streams gradually increases.
#### The Tracks Released Per Year:
![image](https://github.com/user-attachments/assets/c2913f62-49cd-4abd-8636-17f4da4b6164)
  - Comparing the monthly release of tracks shows that January and May have the highest peaks of tracks released; March had a peak but not as high as the ones mentioned earlier, and August had the lowest number of tracks released among the months. After May, the number of tracks released goes down and then rises again after August.
#### The Number of Tracks Released Every Month:
![image](https://github.com/user-attachments/assets/c11b01c8-ecf0-49fb-b423-cde3c496b607)

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
  - **Answer:** Based on my observation 

## Documentation

### October 21, 2024

#### Overview of the Dataset
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
  - When I reran the code, it showed an error that said "ValueError." What I did was change the code from `.astype(float)` to `pd.to_numeric(Spot_Data['streams'], errors = 'coerce')`, and it worked.
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
  - I noticed that the graph for the Released Year was too small and hard to read. I found a solution to make it more readable by adjusting the number of bins:
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

  - I assumed that "NaN" was not counted, so I used `.dropna()` to exclude it:
    ```
    top_five = spot_data['streams'].sort_values().tail(6).iloc[::-1].reset_index()
    top_five.dropna()
    ```
    ![image](https://github.com/user-attachments/assets/7e1d177a-63da-40a4-b2c7-f9f021b33b5a)

### October 24, 2024
  - In the basic descriptive statistics section, I updated the graph by adding a Kernel Density Estimate (KDE) and a grid for readability. The new code is:
    ```
    sns.histplot(spot_data['released_year'], color='orange', bins = 50, kde = True) # Generate the histogram for the released year using Seaborn
    sns.histplot(spot_data['artist_count'], color='green', kde = True) # Generate the histogram for the artist count using Seaborn
    ```

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
  - I realized when coding for the correlation of streams and danceability and energy that I could use the main dataframe to call the data instead of creating a separate line of code specifically calling the two columns I needed. I used the same code from my previous code in the "Number of Tracks Released Every Month" since I was using the same type of graph, but I realized that I did not need to group the values.
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
---

## Libraries Utilized
  - Pandas
  - Matplotlib.pyplot
  - Seaborn

## Authors
  - Kyle Nathaniel V. Dimalanta

## Version History
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
  - https://www.westga.edu/academics/research/vrc/assets/docs/scatterplots_and_correlation_notes.pdf
  - https://seaborn.pydata.org/generated/seaborn.histplot.html
  - https://stackoverflow.com/questions/759
  - https://seaborn.pydata.org/generated/seaborn.histplot.html
  - https://stackoverflow.com/questions/15891038/change-column-type-in-pandas/28648923#28648923
  - https://stackoverflow.com/a/53361168/23541370
