# Data Modeling with Postgres

## Introduction
A startup names Sparkify is a digital music streaming service that gives access to millions of songs and other content from artists all over the world. The company wants to analyze the users and songs data that it is currently collecting on their streaming app. The analytics team is interested in understanding what songs, genre or artists users are listening to, so that they can provide targeted marketing to increase the brand value and revenue of the company. The data currently resides in a directory of JSON logs on user activity on the app, and a directoy of JSON metadata on the available songs on the app.
The company is expecting a Data Engineer to process these logs and metadata files and store it in a Postges database optimized to provide song play analysis. This project creates a Postgres schema and ETL pipelines to store the data in the form of tables representing star schema for faster access and analysis of data.

## Data Model
The data model resembles a star schema with one Fact table, songplays and four dimension table: users, songs, artists and time. A star schema provides the advantages of higher query performance, built-in referential integrity and ease of understanding.
![image](https://drive.google.com/uc?export=view&id=1BgUXfkibD25e1wbxmAYD4LUzHRwzFht9)

## ETL Pipeline
There are 5 files in the ETL_Files folder, which are explained in detail below:
- sql_queries.py: This python file has queries for dropping and creating tables. It creates a python list for all the drop and create queries. The files also contains queries for inserting data into the tables.
- create_tables.py: This python file imports the contents of the sql_queries.py file. It creates the database, drops the tables, if they exist and then re-creates the tables. This script is a way of resetting the database amd its tables.
- etl.ipynb: This python file has queries for dropping and creating tables. It creates a python list for all the drop and create queries. The files also contains queries for inserting data into the tables.
- test.ipynb: This python file has queries for dropping and creating tables. It creates a python list for all the drop and create queries. The files also contains queries for inserting data into the tables.
- etl.py: This python file has queries for dropping and creating tables. It creates a python list for all the drop and create queries. The files also contains queries for inserting data into the tables.
