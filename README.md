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

