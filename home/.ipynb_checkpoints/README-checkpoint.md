## Sparkify Analytics:

In this project we wanted to create a platform to organise our data , for easy access and robust availabity for analytics in Sparkify.
It will help analysts in understanding what songs users are listening to, and give valuable insights on the data. 
For the music streaming startup we designed a star-schema , data warehouse , built ETL-Pipelines and processes. 


## Getting Started:
Instruction will help  to prepare the database with the relevant data and executing the ETL Pipeline.


## Prerequisites:
Familiarity with Postgres, and Python basics.

## Files:
Two file are used as the source datasets for the project which are published in the folder
- data/song_data/
- data/log_data/

Notes: We can use a subsets of the data for testing, in which case please be aware of the referential intigrity .

## Scripts Involved:

- create_tables.py
- etl.py
- sql_queries.py

#### create_tables.py :

This script is used to create the sparkify database and run the create_table_queries and drop_table_queries modules from 
sql_queries.py, drop the already existing database objects and create the tables needed to import the song and log data.

#### etl.py
This script will import all data and apply all logics using the functions `process_song_file()`,`process_log_file()`,`process_data()` and 
the script `sql_queries.py`

#### Fact Table:(songplays)
Records in log data associated with song plays i.e. records with page `NextSong`
- songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
#### Dimension Tables:

#### users
users in the app
- user_id, first_name, last_name, gender, level
#### songs
 songs in music database
- song_id, title, artist_id, year, duration

#### artists 
artists in music database
- artist_id, name, location, latitude, longitude
#### time 
timestamps of records in songplays broken down into specific units
- start_time, hour, day, week, month, year, weekday

#### Notes:

Run `test.ipynb` and `etl.ipynb` is created  to confirm the creation of your tables with the correct columns and interpret the results step by step. (For testing purposes only)

## Executing the scripts:
 - step1 :Reset/Drop and Create the tables 
`python create_tables.py`
- step2: Import data with etl scripts:
`python etl.py`

