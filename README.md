# kafka_sm
Learning project for Kafka steaming simulated data from stock market to AWS S3 for analysis via AWS Athena

## Learning Kafka and AWS

I wanted to start learning the basics of Apache Kafka and AWS so I decided to start this project to get introduced to the two topics. In this project I deployed Kafka on an AWS EC2 instance. To see the whole pipeline architecture please see [Architecture.jpg](https://github.com/pjvalent/kafka_sm/blob/main/Architecture.jpg)

### Dataset and Producet
For this project I have started with a dataset in the form of a csv. This csv contains stock trading data that is randomly sampled and fed into Kafka. The producer is written utilizing Python and will load the csv as a dataframe, and then randomlly sample the dataframe at 1 second intervals, it will continue to do this indeffinetly.

> I plan on updating this to pull data from a free stock market API once a suitable one is found

### Consumer, Data Store, and Analysis

For the Consumer I also utilized Python to connect to kafka and then load the data into an AWS S3 bucket. After loading the data into S3, I then created an AWS Glue crawler and ran it on the S3 bucket so that I would be able to query the data in AWS Athena. These systems are all AWS specific and as such I am unable to provide them here.

> Future ideas for the analysis are to make a dashboard for analyzing the data
