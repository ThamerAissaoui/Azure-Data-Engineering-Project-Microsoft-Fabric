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

The Jupyter Notebook Python code is located here: https://github.com/ThamerAissaoui/Azure-Data-Engineering-Project-Microsoft-Fabric/blob/main/Process_bing_news.ipynb

     



