# Azure-Data-Engineering-Project-Microsoft-Fabric
Bing News Data Analytics- End-to-End Azure Data Engineering Project using Microsoft Fabric.

A revolutionizing cutting-edge all-in-one data Engineering and Data science platform, from ingestion to reporting, leveraging incredible machine learning and deep learning capabilities and seamlessly integrating Copilot for Power BI, this is Microsoft Fabric, Built for the Era of AI!

<img src="https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/blob/main/WORKFLOW.gif" align="center"/> 

Our journey in this quick tutorial will look like the following agenda:

In the initial phase, we will leverage Data Factory to establish a connection with the Bing API and extract the most recent news data, storing it in the lake database in JSON format. 
Subsequently, utilizing the Synapse data engineering tool, we will process the raw JSON file, converting it into a refined Delta table. 

Following this, employing the Synapse data science tool, we will employ a text analysis machine learning model to predict the sentiment of the acquired news data and incorporate the results into the Lake database. 

Next, utilizing Power BI, we will construct a new dashboard incorporating the latest data. 

Finally, utilizing the Data Activator tool, we will configure alerts within Power BI visuals to disseminate notifications via Microsoft Teams or email channels.

## Environment Setup
![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/15b966bc-dd1b-4a2c-9cae-336590cc60b5)

To use Fabric, we have to activate it within the Power BI workspace:

![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/ebade1bf-e9c5-43db-80a6-f8e445fda981)

We have to set up a Lakehouse to use as a Data Lake similar to Azure Data Lake Gen2:
![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/562532ba-41fd-4fc6-8bf5-1f73568e3a6b)


## Data Ingestion

First, create an ingestion pipeline using the Data factory:
![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/bb3e8d96-efcb-47d3-a57d-3b51cdb8c605)

Copy the latest news from Bing API using a parametrized search query :
![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/71faf85a-b7d8-4172-98c1-81cca8d871b3)

The destination of this pipeline ingestion job should be saved to our Lakehouse in JSON format:
![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/1aaf9254-ce1c-40e2-8fd9-83d57ef1e40e)

## Data Transformation (Incremental Load)

We have used Synapse Data Engineering to create the notebooks and define the Spark jobs.

We have 2 types of Incremental load:

### Type 1:
![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/ae7fcfef-e034-450a-952e-9a34b688d45d)

### Type 2:

![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/aa219ecb-88dc-4c8f-9a85-04cf6efc3692)

We will be considering Type 1 for our project, we will be overwriting any existing data and we won't keep any history.

The Jupyter Notebook Python code is located here: [Data Transformation (Incremental Load)](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/blob/main/Process_bing_news.ipynb)


## Sentiment Analysis (Incremental Load)

We have used Synapse Data Engineering to create the notebooks and define the Spark jobs.

We have considered A pre-trained Machine learning model from Synapse ML to analyze the sentiment of the news: Positive, Neutral, or Negative based on the description, then we saved the output to 

The Jupyter Notebook Python code is located here: [Sentiment Analysis (Incremental Load)](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/blob/main/news-sentiment-analysis.ipynb)

## Data Reporting using Power BI

![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/c295132a-01a2-4bf5-8c93-d70e39b826e1)

## Building Pipelines and E2E testing
Now it is time to create a complete E2E pipeline that will be triggered automatically every day at 6 AM

![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/b233601c-1e4b-4ee9-85ff-61f49a27b45b)


## Setting up alerts (Data Activator)

Data activator coming new feature: monitoring and alerting tool where it monitors the data continuously and if it finds some anomalies or outliers in the data it will trigger an alert for us to take some actions immediately

Create a new reflex component:

![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/d2b18371-a87a-4267-8c55-84c0e2e19b8f)

![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/37eed0ed-5303-4e26-a22f-463d07a82bed)

You can then define any Trigger condition you judge relevant to your use case:

![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/95708da8-c37a-47c9-9729-a02e60bfc163)
Notification received:
![image](https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/assets/36975418/449ef043-9bf8-46d2-a399-ebbd0935386a)





     



