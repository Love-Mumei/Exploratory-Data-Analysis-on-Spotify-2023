# Love Mumei Exploratory Data Analysis on Spotify 2023

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
![image](https://github.com/user-attachments/assets/5ba30fb0-df94-428b-bf9d-4c956df5844f)
  #### Distribution of Artist Count:
![image](https://github.com/user-attachments/assets/48026347-8d48-498e-9abb-7502feb00ab8)
# Top Performers
  -The highest number of streams: 3.703895e+09
  #### Top 5 performers:
  ![image](https://github.com/user-attachments/assets/6a393ad9-4abf-4947-b908-6180a85bf7b7)

# Documentation
  ## October 21, 2024
  ### Overview of the dataset
  - Realizing that the data type for the 'streams' column is wrong, I used .astype(float) on the 'streams' column to convert the datatype from Object to Float. The code snippet is:
     ```
     spot_data['streams'] = pd.to_numeric(Spot_Data['streams'], errors = 'coerce')
     spot_data.dtypes
     ```
     #### Output before conversion:
          streams                 object
     #### Output after conversion:
          streams                 float64
  ## October 22, 2024
  ### Overview of the dataset
  - when I reran the code, it showed an error that said "ValueError." What I did was change the code from .astype(float) to pd.to_numeric(Spot_Data['streams'], errors = 'coerce'), and it worked.
  - PD.to_numeric() converts it from object to float as when I looked at the raw data, it is in exponential form, and making it into integers will have an int casting error.
  - The code snippet is:
    ```
    spot_data['streams'] = pd.to_numeric(Spot_Data['streams'], errors = 'coerce') #Convert the Data from Object to Float.
    spot_data['streams'].dtypes
    ```
  - The output datatype remained the same, but I changed it a bit so that it will be more understandable when looking at it
    #### Output before the conversion:
        dtype('O')
    #### Output after the conversion:
        dtype('float64')
  ### Basic Descriptive Statistics
  - After Converting the 'streams' column from Object to Float it's time to du-du-du-duel jkjk time to find the mean, median, and standard deviation:
    ```
    #Find the Mean
    data_mean = spot_data['streams'].mean()
    print("Mean:", data_mean)

    # Find the Median
    data_mid = spot_data['streams'].median()
    print("Median:", data_mid)

    # Find the Standard Deviation
    data_std = spot_data['streams'].std()
    print("Standard Deviation:", data_std)
    ```
    #### Outputs
    ![image](https://github.com/user-attachments/assets/928991e8-c9e6-4a7e-a855-6b668bdfa54a)
  - Then, I look for the frequencies of the data for the Artist Count and Release Year using the code:
    ```
    freq_release = spot_data['released_year'].value_counts() #Find the Frequency for Each year.
    freq_release

    freq_artist = spot_data['artist_count'].value_counts() # Generate the Data for the Artist count
    freq_artist
    ```
  - Use histplot to distribute the Artist Count and Released year in a graph using Seaborn.
    #### Generate the Release Year Histogram:
        sns.histplot(spot_data['released_year'], color='orange') #Generate the histogram using Seaborn
        #Use matplot to modify the graph and show the graph
        plt.title('Distribution of Released Year')
        plt.xlabel('Released Year')
        plt.ylabel('Frequency')
        plt.show()
    #### Generate the Artist Count Histogram:
        sns.histplot(spot_data['artist_count'], color='green') #Generate the histogram using Seaborn
        #Use matplot to modify the graph and show the graph
        plt.title('Count of Artist Count')
        plt.xlabel('Artist Count')
        plt.ylabel('Frequency')
        plt.show()
## October 23,2024
### Basic Descriptive Statistics
  - I noticed that the generated graph in Released Year it looks too small and hard to read. So I looked up on some solution on how to make it readable and I found out that bins make it readable and summarizes the graph
    ```
    sns.histplot(spot_data['released_year'], color='orange', bins = 50) #Generate the histogram using Seaborn
    #Use matplot to modify the graph and show the graph
    plt.title('Distribution of Released Year')
    plt.xlabel('Released Year')
    plt.ylabel('Frequency')
    plt.show()
    ```
    #### The previous graph for the Released Year:
    ![image](https://github.com/user-attachments/assets/51619a33-fe38-4910-bf95-20380b20e5b5)
    #### The new graph for the Released Year:
    ![image](https://github.com/user-attachments/assets/fd19344b-a152-4387-8b24-5d474598c343)
  ### Top Performance
  - When I was Sorting the values of streams, I found out that the last value is "NaN," and when ranking, the code and output looks like this:
    ```
    top_five = spot_data['streams'].sort_values().tail(6).iloc[::-1].reset_index()
    top_five
    ```
    ![image](https://github.com/user-attachments/assets/3e77a762-6453-414e-9d0c-2a8ad312e768)
  - I assumed that "NaN" is not counted, which is why the tail has a six instead of 5. So, looking for a solution, I found the code .dropna()
    ```
    top_five = spot_data['streams'].sort_values().tail(6).iloc[::-1].reset_index()
    top_five.dropna()
    ```
    ![image](https://github.com/user-attachments/assets/7e1d177a-63da-40a4-b2c7-f9f021b33b5a)
## October 24, 2024
  - So, I changed the graph again. I added a Kernel Density Estimate or KDE when looking through the Seaborn site cited below and a grid for readability. The new code is:
    ```
    sns.histplot(spot_data['released_year'], color='orange', bins = 50, kde = True) #Generate the histogram for the released year using Seaborn
    sns.histplot(spot_data['artist_count'], color='green', kde = True) #Generate the histogram for the artist count using Seaborn
    ```
### Before(released year):
![image](https://github.com/user-attachments/assets/fd19344b-a152-4387-8b24-5d474598c343)
### After:
![image](https://github.com/user-attachments/assets/5ba30fb0-df94-428b-bf9d-4c956df5844f)
Before (artist count):
![image](https://github.com/user-attachments/assets/b364d215-305b-4902-8206-ab2a209bfb95)
After:
![image](https://github.com/user-attachments/assets/48026347-8d48-498e-9abb-7502feb00ab8)

# Libraries Utilized
  - Pandas
  - Matplotlib.pyplot
  - Seaborn
# Authors
  - Kyle Nathaniel V. Dimalanta
# Version History
## 0.4 - October 24, 2024
  - Start creating the Temporal Trends
  - Added the KDE to the graph to make it look more presentable.
  - Edited the Title of README
## 0.3 - October 23, 2024
  - Create the Data Analysis for the "Top Performers"
  - Fix the Histogram for the Release year to make it more readable and summarize the graph.
## 0.2 - October 22, 2024
  - Add Matplot and Seaborn Libraries
  - Fix the value error when converting the Column 'streams' from object to float data type
## 0.1 - October 21, 2024
  - Find the Mean, Median, and Standard Deviation of the 'streams' column
  - Create the Data Analysis for the "Overview of Dataset
  - Fix the data type of the 'streams' so that it will be a float instead of an object
  - Fix the encoding parameter to 'latin1' because 'UTF-8' shows an error
  - Load the csv file
# References:
  - https://seaborn.pydata.org/generated/seaborn.histplot.html
  - https://stackoverflow.com/questions/75931562/remove-the-white-gaps-or-no-data-regions-from-the-histogram
  - https://seaborn.pydata.org/generated/seaborn.histplot.html
  - https://stackoverflow.com/questions/15891038/change-column-type-in-pandas/28648923#28648923
  - https://stackoverflow.com/a/53361168/23541370
