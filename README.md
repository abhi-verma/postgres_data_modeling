# Data Modeling with Postgres

## Introduction
A startup names Sparkify is a digital music streaming service that gives access to millions of songs and other content from artists all over the world. The company wants to analyze the users and songs data that it is currently collecting on their streaming app. The analytics team is interested in understanding what songs, genre or artists users are listening to, so that they can provide targeted marketing to increase the brand value and revenue of the company. The data currently resides in a directory of JSON logs on user activity on the app, and a directoy of JSON metadata on the available songs on the app.
The company is expecting a Data Engineer to process these logs and metadata files and store it in a Postges database optimized to provide song play analysis. This project creates a Postgres schema and ETL pipelines to store the data in the form of tables representing star schema for faster access and analysis of data.

## Data Model
The data model resembles a star schema with one Fact table, songplays and four dimension table: users, songs, artists and time. A star schema provides the advantages of higher query performance, built-in referential integrity and ease of understanding.
