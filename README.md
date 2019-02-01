# Udacity - Big Data - Apache Spark

## Installation
The following was used for the environment setup:

- Python 3.5
- PySpark SQL
- PySpark ML

## Project Motivation
For a  fictional music streaming service (Sparkify), we are interested in seeing if we can predict which users are at risk of cancelling their service.  The goal is identify these users before they leave so they can hypothetically receive discounts and incentives to stay.

## File Descriptions
- Sparkify.ipynb - Notebook used for initial analysis / training.  Used a small subset (128MB) for this analysis.  When performed on the IBM platform, the entire dataset (12GB) will be used.
- README.md - The file you are reading now

## Feature Engineering
As a result of using Logistc Regression, I was able to get a training accuracy of around 99.99% and a testing accuracy of around 99.98%.  This was due to the following transformations to the data:

String Indexer:
- Gender_indexer (inputCol="gender")
- User_indexer (inputCol="userAgent")
- Page_indexer (inputCol="page")
- indexer (inputCol="Churn")

One Hot Encoding: 
- Gender_encoder (inputCol='Gender_Index')
- User_encoder (inputCol='User_Index')
- Page_encoder (inputCol='Page_Index')

Vector Assembler:
- assembler (inputCols=["Gender_Vec", "User_Vec", "Page_Vec", "status"])

## Acknowledgements
The data was taken from the following (https://s3.amazonaws.com/video.udacity-data.com/topher/2018/December/5c1d6681_medium-sparkify-event-data/medium-sparkify-event-data.json)
