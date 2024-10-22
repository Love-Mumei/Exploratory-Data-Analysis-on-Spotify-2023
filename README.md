# Love-Mumei-Exploratory-Data-Analysis-on-Spotify-2023

# Overview of the DataSet
  - Number of Rows: 953
  - Number of Columns: 24
  - Datatypes on each column:
     - **Object:** track name, artist(s) name, streams, in Spotify playlists, in Apple playlists, in Deezer playlists, in Shazam charts, key, mode
     - **Int64:** artist count, released year, released month, released day, in Spotify charts, in Apple charts, in Deezer charts, bpm, danceability, valence, energy, acousticness, instrumentalness, liveness, speechiness
# Basic Descriptive Statistics
  - Mean: 514137424.93907565
  - Median: 290530915.0
  - Standard Deviation: 566856949.0388832
  #### Distribution of Release Year:
![image](https://github.com/user-attachments/assets/51619a33-fe38-4910-bf95-20380b20e5b5)
  #### Distribution of Artist Count:
![image](https://github.com/user-attachments/assets/b364d215-305b-4902-8206-ab2a209bfb95)

# Documentation
  ## October 21, 2024
  - Realizing that the data type for the 'streams' column is wrong, I used .astype(float) on the 'streams' column to convert the datatype from Object to Float. The code snippet is:
     ```
     Spot_Data['streams'] = pd.to_numeric(Spot_Data['streams'], errors = 'coerce')
     Spot_Data.dtypes
     ```
     ### Output before conversion:
          streams                 object
     ### Output after conversion:
          streams                 float64
  ## October 22, 2024
  - when I reran the code, it showed an error that said "ValueError." What I did was change the code from .astype(float) to pd.to_numeric(Spot_Data['streams'], errors = 'coerce'), and it worked.
  - PD.to_numeric() converts it from object to float as when I looked at the raw data, it is in exponential form, and making it into integers will have an int casting error.
  - The code snippet is:
    ```
    Spot_Data['streams'] = pd.to_numeric(Spot_Data['streams'], errors = 'coerce') #Convert the Data from Object to Float.
    Spot_Data['streams'].dtypes
    ```
  - The output datatype remained the same, but I changed it a bit so that it will be more understandable when looking at it
    ### Output before the conversion:
        dtype('O')
    ### Output after the conversion:
        dtype('float64')
  - First I look for the frequencies of the data for the Artist Count and Release Year using the code:
    ```
    Freq_release = Spot_Data['released_year'].value_counts() #Find the Frequency for Each year.
    Freq_release

    Freq_artist = Spot_Data['artist_count'].value_counts() # Generate the Data for the Artist count
    Freq_artist
    ```
  - Use histplot to distribute the Artist Count and Released year in a graph using Seaborn.
    ### Generate the Release Year Histogram:
        sns.histplot(Spot_Data['released_year'], color='orange') #Generate the histogram using Seaborn
        #Use matplot to modify the graph and show the graph
        plt.title('Distribution of Released Year')
        plt.xlabel('Released Year')
        plt.ylabel('Frequency')
        plt.show()
    ### Generate the Artist Count Histogram:
        sns.histplot(Spot_Data['artist_count'], color='green') #Generate the histogram using Seaborn
        #Use matplot to modify the graph and show the graph
        plt.title('Count of Artist Count')
        plt.xlabel('Artist Count')
        plt.ylabel('Frequency')
        plt.show()

# Libraries Utilized
  - Pandas
  - Matplotlib.pyplot
  - Seaborn
# Authors
  - Kyle Nathaniel V. Dimalanta
# Version History
## 1.1 - October 22, 2024
  - Add Matplot and Seaborn Libraries
  - Fix the value error when converting the Column 'streams' from object to float data type
## 1.0 - October 21, 2024
  - Find the Mean, Median, and Standard Deviation of the 'streams' column
  - Fix the data type of the 'streams' so that it will be a float instead of an object
  - Fix the encoding parameter to 'latin1' because 'UTF-8' shows an error
  - Load the csv file
# References:
  - https://stackoverflow.com/questions/15891038/change-column-type-in-pandas/28648923#28648923
