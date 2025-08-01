
# Build A Fabric Real-Time Intelligence Solution in a Day 
### Overall Estimated Duration: 4 Hours
## Overview

In this lab, you will explore Real-Time Intelligence, create a Fabric Workspace, and set up an Eventhouse for event-driven data. You will enable OneLake Availability, create an Eventstream, and run a Data Generator Notebook to simulate streaming events. Additionally, you will set up a Lakehouse, upload reference data, access Eventhouse data, build a KQL Database schema, and develop a Real-Time Dashboard with auto-refresh. Finally, you will use Data Activator to automate real-time actions.

## Objective  

Understand how to leverage **Microsoft Fabric** for real-time data processing, analytics, and automation. By the end of this lab, you will have knowledge on:  

- **Setting Up a Fabric Workspace and Eventhouse**: Create a **Fabric Workspace** for project collaboration and set up an **Eventhouse** to efficiently store and process event-driven data.  
- **Integrating Data with OneLake and Eventstream**: Enable **OneLake Availability** for seamless data integration and create a **new Eventstream**, defining its topology to manage real-time data ingestion.  
- **Simulating and Processing Streaming Data**: Import and run a **Data Generator Notebook** to simulate streaming events, then define the **Eventstream topology** for structured data flow.  
- **Building a Lakehouse for Data Storage and Processing**: Set up a **Lakehouse**, upload reference data files, and create **Delta tables** for efficient data storage and processing.  
- **Querying and Structuring Data with KQL**: Access **Eventhouse data** from the Lakehouse and build a **KQL Database schema** to structure and query real-time data effectively.  
- **Creating Real-Time Dashboards and Automating Insights**: Develop a **Real-Time Dashboard**, enable **auto-refresh**, and use **Data Activator** to automate actions based on real-time events.  

## Pre-requisites

Participants should have:  

- **Basic understanding of Microsoft Fabric**: Familiarity with Fabric’s data processing, storage, and analytics capabilities.  
- **Familiarity with real-time data processing concepts**: Understanding of streaming data, event-driven architectures, and analytics workflows.  

## Architecture

In this lab, you will build a Real-Time Intelligence Solution in Microsoft Fabric to analyze web traffic and consumer behavior for an e-commerce website. Using clickstream data, you will leverage Fabric Real-Time Intelligence to track visitor interactions and predict sales trends. The workflow includes streaming events into Fabric Eventhouse via Eventstream, performing real-time data transformations using Kusto Query Language (KQL), and utilizing OneLake availability to seamlessly access data through the Lakehouse. Additionally, you will create real-time visualizations with Fabric Real-Time Dashboards and implement Data Activator Reflex actions to automate alerts and responses based on streaming data.

## Architecture Diagram

![](media/architecture2.png)

## Explanation of Components

The architecture for this lab involves the following key components:

- **Notebook**: Generates and ingests streaming data into the system.  
- **Eventstream**: Acts as a streaming data pipeline, ingesting events from the Notebook into **Eventhouse**.  
- **Eventhouse**: A real-time analytics store that processes and structures streaming data for further use.  
- **Lakehouse**: Serves as a storage layer for structured and unstructured data, accessible via shortcuts from **Eventhouse**.  
- **Real-Time Dashboard**: Visualizes real-time data from **Eventhouse** for monitoring and insights.  
- **Data Activator**: Automates responses and alerts based on real-time streaming data.  

## Getting Started with Lab
Once you're ready to dive in, your virtual machine and lab guide will be right at your fingertips within your web browser.

![](media/guide-01up2.png)

## Virtual Machine & Lab Guide
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.

## Exploring Your Lab Resources
To get a better understanding of your lab resources and credentials, navigate to the **Environment Details** tab.

![](media/getting-started-2upd2.png)

## Utilizing the Split Window Feature
For convenience, you can open the lab guide in a separate window by selecting the Split Window button from the top right corner.

![](media/getting-started-3upd2.png)

## Managing Your Virtual Machine
Feel free to **Start**, **Stop**, or **Restart** your virtual machine as needed from the Resources tab. Your experience is in your hands!

![](media/getting-started-5upd2.png)

## Let's Get Started with Microsoft Fabric portal
 
1. Open the **Microsoft Edge browser** on your desktop and visit `https://app.fabric.microsoft.com/`. You will be navigated to the login page.

    ![](media/guide-58up.png)


2. Enter the following **Username/Email** **1**, and then click on **Submit** **2**.  

    - **Username/Email**:<inject key="AzureAdUserEmail"></inject>

      ![](media/guide-59up.png)

    - **Password**:<inject key="AzureAdUserPassword"></inject> 

      ![](media/loginpwazureportal.png)

3. Click **Sign in** and follow the prompts to sign into Fabric.

4. You will be navigated to the **Fabric Home Page**.

    ![](media/guide-60up.png)

    > **Note:** Click on **Cancel** in the Welcome to Fabric view pop-up.

    To work with Fabric items, you will need a trial license and a workspace that has Fabric license. Let’s set this up.

5. On the top right corner of the screen, Select the **User** **icon (1)**. Select **Free trial (2)**.

    ![](media/image11upd2.png)

6. **Activate your 60-day free Fabric trial capacity** dialog opens. Select **Activate**.

    ![](media/image12upd2.png)

7. The "Successfully upgraded to Microsoft Fabric" dialog will appear. Click on **Fabric Home Page**.      

8. You will be navigated back to the **Microsoft** **Fabric Home page**.

    ![](media/guide-60up2.png)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Click **Next** from the bottom right corner to embark on your Lab journey!

![](media/up4.png)

### Happy Learning!!

