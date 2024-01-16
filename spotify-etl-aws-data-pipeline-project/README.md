# Spotify ETL End-To-End Pipeline Project
<img align="center" alt="coding" width="400" src="https://github.com/Shoaib9288/AWS_DataEngineering_Projects/blob/main/spotify-etl-aws-data-pipeline-project/Spotify.gif">

## Overview
Welcome to the repository for an ETL pipeline that extracts data from the Spotify API, transforms it, and loads it into AWS. This pipeline provides a comprehensive end-to-end solution for retrieving and analyzing music data from Spotify.

## Architecture
![logo](https://github.com/Shoaib9288/AWS_DataEngineering_Projects/blob/main/spotify-etl-aws-data-pipeline-project/Snapshots/Architecture.jpeg)

## About Spotify API
The Spotify API is a web-based platform that provides developers with access to Spotify's music data and services. It allows developers to build applications that can interact with Spotify's music streaming platform, enabling users to browse and play music, manage playlists, search for songs, and access metadata about artists, albums, and tracks.

In this project we have used the Top 50 - India Playlist as our data

## Services Used
Amazon S3: Amazon Simple Storage Service (S3) is a cloud-based object storage service provided by Amazon Web Services (AWS). It is designed to store and retrieve large amounts of data, such as photos, videos, and other types of files, from anywhere on the web
CloudWatch: Amazon CloudWatch is a monitoring and observability service provided by Amazon Web Services (AWS). It is designed to collect and track metrics, collect and monitor log files, and set alarms
AWS Glue Crawler: AWS Glue Crawler is a service that automatically crawls data stores, such as Amazon S3, RDS, and Redshift, to infer schemas and partition structures. It can also identify changes in schemas and update the Data Catalog accordingly.
AWS Lambda: AWS Lambda is a serverless computing service provided by Amazon Web Services (AWS). It enables developers to run code without provisioning or managing servers. Lambda runs code in response to events and automatically scales up or down to match the incoming request traffic.
AWS Athena: Amazon Athena is an interactive query service provided by Amazon Web Services (AWS) that makes it easy to analyze data stored in Amazon S3 using standard SQL. It allows users to quickly and easily query data without having to set up and manage complex infrastructure or data warehousing tools.
Data Catalog: The Data Catalog is a central repository that stores metadata about data sources, tables, and transforms, which can be queried and managed by other AWS services, such as Athena and EMR.

## Install Packages
```
pip install pandas
pip install boto3
pip install spotipy
pip install numpy
```

## Execution Flow
The project extracts data through the Spotify API.
CloudWatch triggers a Lambda function once a week.
The Lambda function extracts data and stores it in the raw folder in S3.
Another Lambda function transforms the raw data and stores it in the transformed folder in S3.
AWS Glue Crawler is used to crawl the album, artists, and songs data and provide it to the data catalog.
Amazon Athena is used to query and analyze data in the data catalog.
