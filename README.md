# Project 2: Data Modeling with Apache Cassandra

This **Data Engineering Nanodegree** project creates an Apache Cassandra database `sparkify` for a music app, *Sparkify*.
The purpose of the NoSQL database is to answer queries on song play data. The data model includes a table for each of the following queries:

1. Give me the artist, song title and song's length in the music app history that was heard during  sessionId = 139, and itemInSession  = 4

2. Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 9
    
3. Give me every user name (first and last) in my music app history who listened to the song 'Pump It'


## Data pre-processing, ETL pipeline, and data modeling

The data are stored as a collection of csv files partitioned by date. The ETL pipeline and data modeling are written in a single jupyter notebook, **Project_1B_Project_Template.ipynb**.

ETL copies data from the date-partitioned csv files to a single csv file **event_datafile_new.csv** which is used to populate the denormalized Cassandra tables optimised for the 3 queries above. The 3 tables in the model are named after the song play query they are created to solve:

1. **`songs_listned_by_session`** 

2. **`songs_listened_by_user`** 

3. **`user_listend`**

The example queries are returned as pandas dataframes to facilitate further data manipulation.