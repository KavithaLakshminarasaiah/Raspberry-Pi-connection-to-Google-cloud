Google cloud with Raspberry Pi

**Introduction **

Internet of Things (IoT), the embedding of connected computing into everyday devices, has already emerged as a major trend and is projected to continue to expand rapidly in the coming years. In this report, we are going to build a data pipeline that starts with an Internet of Things (IoT) device that captures heart rate, leverages IoT Core to securely publish the data to a message queue where it will then be transported into a data warehouse. A Raspberry Pi with a heart rate sensor will be used for the IoT device and several components of the Google Cloud Platform will form the data pipeline. After completing the steps below, you will have a streaming data pipeline feeding a data warehouse where it can be retrieved to graphically display heart rate data over time.

![image](https://user-images.githubusercontent.com/83789235/117398516-21deba80-aec4-11eb-9ef1-dcdfe1e6c86b.png)

 

1. **Hardware requirements**

•	Raspberry Pi Zero W with power supply, SD memory card and case
•	USB card reader
•	USB hub (to allow for connecting a keyboard and mouse into USB port on the Raspberry Pi)

2. **Using IoT Core to Stream Heart Rate Data**
Using your google account sign up to the Google Cloud Platform console - console.cloud.google.com, Follow the below steps Using IoT Core to Stream the live Heart Rate Data by connecting your Raspberry Pi device.

**Step 1:** Create a new project with name ‘iot-heartrate’. 
**Step 2:** Enable API’s as shown below. Click on Enable APIs and Services
**Step 3:** Create a BigQuery table. BigQuery is a serverless, highly scalable, low cost enterprise data warehouse. From the Cloud Console, select BigQuery and then Create new dataset – “heartRateData"  

 
**Step 4:** Create a Pub/Sub topic and subscription

Cloud Pub/Sub is a simple, reliable, scalable foundation for streaming data and event-driven computing systems. From the Cloud Console, select Pub/Sub and then Topics. Click on the Create a topic button. Enter "heartratedata" as the topic name and then click Create. Now create the new subscription by clicking the 3 dots next to the topic name as shown below. Enter "heartratedata" as the subscription name then click Create

**Step 5:** Use a Dataflow Template

From the Cloud Console, select Dataflow. Click on Create Job from Template. Give the job a name and select the Pub/Sub Subscription to Big/Query template. Click on Run Job.

 

**Step 6: **Create an IoT Core registry and Add the device to the IoT Core Registry

 



**Step 7: **Start the data by using following steps on the terminal/cmd prompt.

 

3. **Output:**

If data is flowing properly then we will see the results when execute the select query on the table. 

Visualize the data using Google Sheets as shown below.

 
**Summary:**

This report shows the procedure to use Google cloud. Explain the Steps in detail needed to create Google Pub/Sub, data pipeline, Google Cloud Dataflow template and leverage Google BigQuery. The output above shows that we have created an entire data pipeline. In doing so, we have used Google IoT Core to secure IoT devices and to allow data to flow into Google Pub/Sub, deployed Dataflow from a template and pushed data into BigQuery and then used the integration with Google Sheets to perform a quick data visualization.

![image](https://user-images.githubusercontent.com/83789235/117398085-25257680-aec3-11eb-862d-1fd87da88e76.png)
