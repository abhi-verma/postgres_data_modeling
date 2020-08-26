# Data Modeling with Postgres

## Introduction
A startup names Sparkify is a digital music streaming service that gives access to millions of songs and other content from artists all over the world. The company wants to analyze the users and songs data that it is currently collecting on their streaming app. The analytics team is interested in understanding what songs, genre or artists users are listening to, so that they can provide targeted marketing to increase the brand value and revenue of the company. The data currently resides in a directory of JSON logs on user activity on the app, and a directoy of JSON metadata on the available songs on the app.
The company is expecting a Data Engineer to process these logs and metadata files and store it in a Postgres database optimized to provide song play analysis. This project creates a Postgres schema and ETL pipelines to store the data in the form of tables representing star schema for faster access and analysis of data.

## Data Model
The data model resembles a star schema with one Fact table, songplays and four dimension table: users, songs, artists and time. A star schema provides the advantages of higher query performance, built-in referential integrity and ease of understanding.
![image](https://drive.google.com/uc?export=view&id=1BgUXfkibD25e1wbxmAYD4LUzHRwzFht9)

## Project Structure
```
postgres_data_modeling
│   README.md             # Project description
│
└───Data                  # The dataset
|   |               
│   └───log_data
│   |   │  ...
|   └───song_data
│       │  ...
│   
└───Src                   # Source code
│   |
|   └─── create_tables.py # Schema and Tables creation script
│   |
|   └─── etl.py           # ETL script
│   |
|   └─── sql_queries.py   # SQL DDL Queries
│   |
|   └─── etl.ipynb        # ETL helper Jupiter notebook
│   |
|   └─── test.ipynb       # Tables Data Test Jupiter Notebook
```



## ETL Pipeline
There are 5 files in the Src folder, which are explained in detail below:
- sql_queries.py: This python file has queries for dropping and creating tables. It creates a python list for all the drop and create queries. The files also contains queries for inserting data into the tables.
- create_tables.py: This python file imports the contents of the sql_queries.py file. It creates the database, drops the tables, if they exist and then re-creates the tables. This script is a way of resetting the database amd its tables.
- etl.ipynb: This Jupyter Notebook is used for exploring the data sets and insert a small subset to test the tables and the data types.
- etl.py: This python file is the core of the project and builds ETL pipelines to process JSON files and store data into created Postgres tables. The file scans the directory for songs and logs and processes each file inside the directory and subdirectories. It then tranforms the processed data to store it in tables in specific formats.
- test.ipynb: This Jupiter notebook could be used to validate the data inserted into the tables. It connects to the Sparkify database and queries the tables.

## Prerequisites
- Python 3
- pandas and psycopg2 libraries
- Postgres database available on localhost

## Running the Python Scripts
Run the following commands in order:
1. python create_tables.py
2. python etl.py

## Example Queries
1. Which songs were played the most in the year 2018?
2. Which artist was most popular in the year 2018?
3. How much time free users spend listening on the app and could they be targeted for paid subscription marketing?
