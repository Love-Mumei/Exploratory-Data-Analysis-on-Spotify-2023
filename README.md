# Love-Mumei-Exploratory-Data-Analysis-on-Spotify-2023

# Overview of the DataSet
  - Number of Rows: 953
  - Number of Columns: 24
  - Datatypes on each column:
     - **Object:** track name, artist(s) name, streams, in Spotify playlists, in Apple playlists, in Deezer playlists, in Shazam charts, key, mode
     - **Int64:** artist count, released year, released month, released day, in Spotify charts, in Apple charts, in Deezer charts, bpm, danceability, valence, energy, acousticness, instrumentalness, liveness, speechiness
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
# Libraries Utilized
  - Pandas
# Authors
  - Kyle Nathaniel V. Dimalanta
# Version History
## 1.1 - October 22, 2024
  - Fix the value error when converting the Column 'streams' from object to float data type
## 1.0 - October 21, 2024
  - Find the Mean, Median, and Standard Deviation of the 'streams' column
  - Fix the data type of the 'streams' so that it will be a float instead of an object
  - Fix the encoding parameter to 'latin1' because 'UTF-8' shows an error
  - Load the csv file
