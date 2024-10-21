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
     Spot_Data['streams'] = Spot_Data['streams'].astype(float)
     Spot_Data.dtypes
     ```
     ### Output before conversion:
          streams                 object
     ### Output after conversion:
          streams                 float64
# Libraries Utilized
  - Pandas
# Authors
  - Kyle Nathaniel V. Dimalanta
# Version History
## 1.0 - October 21, 2024
  - Find the Mean, Median and Standard Deviation of streams column
  - Fix the data type of the 'streams' so that it will be a float instead of object
  - Fix the encoding parameter to 'latin1' because 'UTF-8' shows an error
  - Load the csv file
