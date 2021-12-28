## INTRODUCTION

A service for streaming music, called Sparkify, has a welcomed problem. Not only their user base but their song database also expanded. As a result , they want to move their processes and data to the cloud. The data are currently stored in JSON files for both the song information and user behavior. This increase in data size means that analysis and processing becomes slow and computationally expensive. This is the problem we are solving using Amazon Web Services. The aim is to move data from a public S3 buckets to AWS.

## S3 BUCKETS
Bucket 1: SONG_DATA='s3://udacity-dend/song_data'
Bucket 2: LOG_DATA='s3://udacity-dend/log_data'

## PROJECT DETAILS
To achieve our goal, we used the STAR SCHEMA to design our table struture
Our Fact Table: songplays
Our Dimensions Tables:users, songs, artists and time table

To execute this project, kindly follow these steps below:
1. Start an AWS Redshift Cluster and setup the IAM role to AmazonS3ReadOnlyAccess.
2. Launch a terminal.
3. Run 'create_tables.py' to first drop tables if they exist and then create the tables listed above
4. Run etl.py to execute the ETL process.

## FILES DESCRIPTION
dhw.cfg: Configuration file used that contains info about Redshift, IAM and S3
create_tables.py: Script to first drop tables if they exist and then create the tables listed above
sql_queries.py: Contains variables with SQL statement in String formats to CREATE, DROP, COPY and INSERT into tables
etl.py: Executes the queries that extract JSON data from the S3 bucket and ingest them to Redshift
