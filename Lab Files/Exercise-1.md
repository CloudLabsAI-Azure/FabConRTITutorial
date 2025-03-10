# Build A Fabric Real-Time Intelligence Solution in a Day 
## Estimated duration: 60 minutes
In this exercise, you will enable a Microsoft Fabric trial license to access its features, explore Real-Time Intelligence to gain insights from streaming data, utilize the Real-Time Hub for managing real-time data processing, create a Fabric Workspace to organize and collaborate on your projects, and set up an Eventhouse to efficiently store and analyze event-driven data.

## Lab objectives: 
In this lab, you will be able to complete the following tasks:
- Task 1: Enable a Microsoft Fabric trial license
- Task 2: Experience Real-Time Intelligence
- Task 3: Real-Time Hub
- Task 4: Create a Fabric Workspace
- Task 5: Create an Eventhouse

## Task 1: Enable a Microsoft Fabric trial license

1. Open the **Microsoft Edge browser** on your desktop and visit `https://app.fabric.microsoft.com/` in Incognito mode. You will be navigated to the login page.

    ![](../media/lab-01/image5.png)


1. Enter the following email/username, and then click on **Submit**.  

    - **Username/Email**:<inject key="AzureAdUserEmail"></inject>

      ![](../media/lab-01/image6.png)

    - **Password**:<inject key="AzureAdUserPassword"></inject> 

1. Click **Sign in** and follow the prompts to sign into Fabric.

1. You will be navigated to the **Fabric Home**.

    ![](../media/lab-01/image10upd.png)

    To work with Fabric items, you will need a trial license and a workspace that has Fabric license. Let’s set this up.

1. On the top right corner of the screen, select the **user** **icon**.

1. Select **Free Trial**.

    ![](../media/lab-01/image11upd1.png)

1. Upgrade to a free Microsoft Fabric trial dialog opens. Select **Activate**.

    ![](../media/lab-01/image12upd1.png)

1. The "Successfully Upgraded to Microsoft Fabric" dialog will appear. Click on **Fabric Home Page**..  

   ![](../media/lab-01/fabrichome_1.png)

1. You will be navigated back to the **Microsoft** **Fabric Home page**.

    ![](../media/lab-01/image10upd.png)

## Task 2: Real-Time Intelligence Experience Items

1. Select **Workloads** icon on the left of your screen. A dialog with the list of Fabric experiences will open. The list of experiences includes Power BI, Data Factory, Industry Solutions, Real-Time Intelligence, Data Engineering, Data Science and Data Warehouse. Let’s explore.

    ![](../media/lab-01/workload1.png)

1. Click on the **Real-Time Intelligence** experience under **Workloads**.

    ![](../media/lab-01/image17upd1.png)

1. You will be navigated to **Real-Time Intelligence Home page**. You will see **Item types** under **About**, and **Get started** categories. With the **Item type** category notice the items:

    a. **Eventhouse:** Used to create a workspace of one or multiple KQL database(s), which can be shared across projects. Also creates a KQL Database within the Eventhouse.
    
    b. **KQL** **Queryset:** Used to run queries on the data to produce shareable tables and visuals.
    
    c. **Real-Time Dashboard**: A collection of tiles, optionally organized in pages, where each tile has an underlying query and a visual representation.
    
    d. **Eventstream:** Used to capture, transform, and route real-time event stream.
    
    e. **Reflex:** For automatically taking actions when patterns or conditions are detected in changing data.

    ![](../media/lab-01/image18upd1.png)

## Task 3: Real-Time Hub

1. Click on the **Real-Time hub** within the Fabric navigation pane on the left side of the screen.

    ![](../media/lab-01/image19upd1.png)

1. The **Welcome to Real-Time hub** dialogue will open and feel free to select **Take a tour** or select **Get Started**.  

    ![](../media/lab-01/image20.png)

2. The Real-Time hub is the single place for streaming data-in-motion across your entire organization. Every Microsoft Fabric tenant is automatically provisioned with this hub. It enables you to easily discover, ingest, manage, and consume data-in-motion from a wide variety of sources.

3. Within the Real-Time hub you have access to three different types of data integration.

    - **All Data streams**: This Is for your running eventstreams and KQL databases, all the stream outputs from eventstreams and tables from KQL databases automatically show up in Real-Time hub.
    
    - **Streaming sources**: Lists all streaming resources from Microsoft services. Whether it’s Azure Event Hubs, Azure IoT Hub, or other services, you can seamlessly ingest data into Real-Time hub.
    
    - **Fabric events:** Events that are generated via Fabric artifacts and external sources, are made available in Fabric to support event-driven scenarios like real-time alerting and triggering downstream actions. You can monitor and react to events including Fabric workspace item events and Azure Blob Storage events.
    
    - **Azure events:** This list includes system events generated in Azure that you can access. An event can be monitored and rules set that will send notifications or perform actions when activated.  

      ![](../media/lab-01/image21upd.png)

1. In the top-right corner of the Real-Time hub, click on the **\+ Connect data source** button.  

    ![](../media/lab-01/image22.png)

1. A window will appear and will detail the currently available streams of data that are available to integrate into the Real-Time hub. This includes a mixture of Azure sources as well as external cloud streaming sources like Amazon Kinesis, Confluent Cloud Kafka, and Google Cloud Pub/Sub. There is even some sample data available to explore

    ![](../media/lab-01/image23.png)

1. **Close** the Get events window by clicking the “X” in the upper right corner.

## Task 4: Create a Fabric Workspace

1. Now let’s create a workspace with Fabric license. Select **Workspaces** from the navigation bar on the left.

1. Select + **New workspace**.

    ![](../media/lab-01/workspace11.png)

1. The **Create a workspace** dialog opens on the right side of the browser.

1. In the **Name** field enter **RTI_<inject key="DeploymentID" enableCopy="false"></inject>**. 

   >**Note**: The user ID will be unique for each user, and the workspace name must also be unique. Ensure that a green check mark with **"This name is available"** appears below the Name field.

1. If you would like, you can enter a **Description** for the workspace. This is an optional field.

1. Click on **Advanced** to expand the section.

    ![](../media/lab-01/RTI_username.png)

1. Under **License mode**, ensure that **Trial** is selected (it should be the default option), then click **Apply** to create a new workspace.

    ![](../media/lab-01/imag017-1.png)

    >**Note:** If the **Introducing task flows** dialog opens, click on **Got it**.

    ![](../media/lab-01/image28.png)

## Task 5: Create an Eventhouse

1. Click the **\+ New item** box to open a new pane that has all the items you can create in this Fabric workspace.

    ![](../media/lab-01/new_item.png)

1. Search for **Eventhouse(1)** and Select the **Eventhouse(2)** option from store data . As we have talked about this can be viewed  similarly to a Lakehouse in that we can store data but this Eventhouse is focused around real time data.

    ![](../media/lab-01/eventhouse-1.png)

1. In the window that appears, give your Eventhouse the name, **eh_Fabrikam** and click on **Create**.

    ![](../media/lab-01/image32.png)

1. This is where you will ultimately stream data from various sources through the rest of the training today. When the item is created, a window will appear giving you some details about the Eventhouse. Click on the **Get started** button.

    ![](../media/lab-01/image33.png)

1. Take a quick tour of the Eventhouse by following the green tooltips on your screen.  This first one shows that an empty Kusto Query Language (KQL) Database was created with the Eventhouse.

    ![](../media/lab-01/imag021.png)

1. Follow the remainder of the tooltips around the screen to show you where to create additional databases, check the storage in OneLake of the Eventhouse, check the usage of Fabric resources in compute minutes, and finally see what actions have occurred in the Eventhouse.  

2. Within the navigational pane on the left of the Eventhouse, find your KQL Database that was created alongside the Eventhouse and simply click on it to view the database details  

    ![](../media/lab-01/image35.png)

1. This will allow us to still have one tab in the left browser pane to see the overview of our entire Eventhouse and a new tab to focus on the KQL Database properties. One goal that we wish to accomplish in our scenario is to ensure that the data streamed to the KQL database is accessible via OneLake. By enabling this feature, we make the data in this KQL Database easily discoverable through shortcuts to be used in any Lakehouse we may want. Locate the **Database details** section on the right and toggle **On** the “Availability” option.
   

   >**Note**: You will be popped up with a dialogue box, leave all the settings as default and click on **Turn on**.

   ![](../media/lab-01/P1L1T5S9.png)

   ![](../media/lab-01/turn-on-1.png)



1. Return to your **RTI_<inject key="DeploymentID" enableCopy="false"></inject>** workspace by selecting it from the left side of the browser.

    ![](../media/lab-01/rti-2upd1.png)

1. If you see the **Task Flows** option taking up most of the space, select the double up arrow on the right-hand side to minimize it

    ![](../media/lab-01/rti_1.png)

1. You now have the basis for how you will begin to ingest the streaming data into your OneLake. The next step is to create a stream of data that can receive the data in motion.

    ![](../media/lab-01/lab-final.png)

### Task 6. Enable OneLake Availability
In this task, you’ll enable OneLake Availability to automatically copy KQL Database data to OneLake in Delta format, allowing seamless querying through Lakehouse and other tools. It’s best enabled before loading large datasets and can be set per table.

1. When an Eventhouse is created, a KQL Database with the same name is created as well. To open the KQL Database click on the Database **WebEvents_EH** in the section **KQL Databases**.

    ![](../media/lab-01/image_task04_step01.png)

2. After selecting the KQL Database click on the switch **availibility** to activate the OneLake availibility as shown in the screenshot.

    ![](../media/lab-01/image_task04_step02.png)

    >**Note:** Newly created tables will automatically inherit the "OneLake availability" setting from the Database level

3. Now the dialog Turn on OneLake availibility is shown. Ensure that Apply to existing tables is checked and click on the button Turn on.

    ![](../media/lab-01/image_task04_step03.png)

### Task 7: Create a new Eventstream
In this task, you will be streaming events (impressions and clicks events) generated by a notebook. The events will be streamed into an eventstream and consumed by our Eventhouse KQL Database.

1. Select your Workspace in the left pane. In our example it is **RTI Tutorial**. If you have been assigned a Workspace at the start of this lab, choose the workspace name that was provided to you. Then click on **+ New Item**. In the popout window scroll a little bit down and select **Eventstream**.

    ![](../media/lab-01/image_task05_step01.png)

1. Give the Eventstream the name WebEventsStream_ES. Make sure that the checkbox **Enhanced Capabilites** is selected and click on **Create**.

    ![](../media/lab-01/image_task05_step02.png)

1. On the Screen **Design a flow to ingest, transform, and route streaming events** click on Use **Custom Endpoint**. This will create an event hub connected to the Eventstream.

    ![](../media/lab-01/image_task05_step03.png)

1. Insert 'WebEventsCustomSource' as the source name and the click on Add.

    ![](../media/lab-01/image_task05_step04.png)

1. Click on **Publish** and now the Eventstream will be published and the Event Hub will be created.

    ![](../media/lab-01/image_task05_step05.png)

1. To get the information we need for the Notebook, the name of the event hub and a connection string click on the Eventstream source named **WebEventsCustomSource**. In the area below the diagram click on **Keys**. Then click on the copy icon besides the **Event hub name**. Now the event hub name is copied to the clipborad.

    ![](../media/lab-01/image_task05_step06.png)

1. To copy the connection string you first have to click on the view icon. After the connection string is revealed click on the copy icon and copy the connection string to Notepad as well.

    ![](../media/lab-01/image_task05_step07.png)

    >**Note:** To copy the connection string it must be visible.

### Task 8: Import Data Generator Notebook
We use a python notebook to generate a stream of artificial click events. The notebook can be found in this GitHub repository Generate_synthetic_web_events.ipynb.

1. 1. Open the notebook in Github by clicking on this link. In GitHub click on the Download raw file icon on the top right.

    ![](../media/lab-01/image5.png)

1. Save the notebook on your local hard drive. By default it will be stored in the folder Downloads.

1. Now we have to import the notebook into our Fabric Workspace. To aceive this execute the following steps.

1. To import the notebook into your workspace you first have to return to the workspace. To do so click on the icon of your workspace on the left pane. In our example the workspace is named RTI Tutorial. If you have been assigned a Workspace at the start of this lab, choose the workspace name that was provided to you. After changing to the workspace click on the menu Import, select Notebook and then the option From this computer.

    ![](../media/lab-01/image_task06_step01.png)

1. In the pane Import status on the right side select Upload

    ![](../media/lab-01/image_task06_step02.png)

1. Browse to the folder on your local computer where you saved the notebook and select the notebook and click on the button Open.

    ![](../media/lab-01/image_task06_step03.png)

1. After the notebook has been uploaded Fabric will display a message that the notebook has been imported successfully.

    ![](../media/lab-01/image_task06_step04.png)

### Task 9: Run the notebook
Now we have to run the notebook to create the stream of artificial click events for our lab. In order for the Notebook to send the events to the correct Event Hub we have to insert the information we have saved in Task 5 - Create Event Stream.To run the notebook and create our datastream please proceed with the following steps.

DO NOT use an InPrivate browser window. Recommend using a Personal browser window for the Notebook session to connect and run successfully.

1. Click on the Notebook Generate_synthetic_web_events in your Fabric Workspace to open it.

    ![](../media/lab-01/image_task07_step01.png)

1. Paste in the values your copied in Task 5 - Create Event Stream as values for eventHubNameevents and eventHubConnString into the notebook.

    ![](../media/lab-01/image_task07_step02.png)

1. Click Run all at the top left to start generating streaming events.

    ![](../media/lab-01/image_task07_step03.png)

    >**Note:** It can happen that the notebook will throw some errors in cell 1. These errors are caused by libaries that already have been installed in the environment. You can safely ignore these errors. The notebook will execute successfully regardless of these errors.

    ![](../media/lab-01/image_task07_errors.png)

1. Wait a few minutes for the first code cell to finish and it will proceed to next code cells automatically.

1. Scroll down to the last code cell and it should begin to print the generated synthetic events in JSON format. If you see an output similar to the following screenshot everything is set up and the notebooks streams artificial click data to the event hub.

    ![](../media/lab-01/image_task07_step04.png)

### Task 10: Define Eventstream topology
Next we have to create the Eventstream topology that will insert the streamed data into our KQL Database. To aceive this please follow the following steps.

1. Open your Eventstream in your Fabric Workspace. To do so click on the icon of your workspace on the left pane. In our example the workspace is named RTI Tutorial. If you have been assigned a Workspace at the start of this lab, choose the workspace name that was provided to you. After changing to the workspace click on the Eventstream WebEventStream_ES.

    ![](../media/lab-01/image_task08_step01.png)

1. Click on Edit in the top toolbar.

    ![](../media/lab-01/image_task08_step02.png)

1. Click on the node Transform events or add Destination and select Filter from the menu.

    ![](../media/lab-01/image_task08_step03.png)

    >**Note**: Pay attention to the table you can see at the bottom of the screen. Here you can see events that are streamed by notebook to the event already.

1. Click on the pencil icon in the node Filter1 to enter edit mode.

    ![](../media/lab-01/image_task08_step04.png)

1. Provide the following values in the pane Filter on the left side. Then click on Save.

Field	Value
Operation name	ClickEventsFilter
Select a field to filter on	eventType
Keep events when the value	equals
value	CLICK
    ![](../media/lab-01/image_task08_step05.png)

Note: CLICK is in ALL CAPS.

1. It is normal that the node ClickEventsFilter is shown with an error. The error indicates that there is no target for the datastream coming out of the filter. We will fix this in the next step.

1. Click on + icon next to the ClickEventsFilter node. and choose Stream from the context menu.

    ![](../media/lab-01/image_task08_step06.png)

1. Choose Stream from the context menu.

    ![](../media/lab-01/image_task08_step07.png)

1. Click on the pencil in node Stream1 to go to edit mode. Enter ClickEventsStream as name of the Eventstream in the field Stream name. Ensure that the Input data format is Json. Click on the Button Save.

    ![](../media/lab-01/image_task08_step08.png)

1. Click on + icon next to the node ClickEventsStream.

    ![](../media/lab-01/image_task08_step09.png)

1. Select the option Eventhouse in the context menu.

    ![](../media/lab-01/image_task08_step10.png)

1. Click the pencil in node Eventhouse1 to enter edit mode. Provide the following values in the pane Eventhouse.

Field	Value
Event processing before ingestion	Ensure that this option is selected.
Destionation name	ClickEventStore
Workspace	Select RTI Tutorial. If you have been assigned a Workspace at the start of this lab, choose the workspace name that was provided to you.
Eventhouse	Select the Eventhouse WebEvents_EH
KQL Database	Select the KQL Database WebEvents_EH
Destination table	Click on Create new and enter BronzeClicks as name for the new table and click on Done.
Input data format	Ensure that the option Json is selected.
    ![](../media/lab-01/image_task08_step11.png)

Click the button Save after you entered all the values.

1. Click on + sign next to the node WebEventsStream_ES.

    ![](../media/lab-01/image_task08_step12.png)

1. Choose the option Filter from the context menu.

    ![](../media/lab-01/image_task08_step13.png)

1. Delete the connection between the new filter node Filter1 and the node ClickEventsFilter by clicking on the trashcan icon.

    ![](../media/lab-01/image_task08_step14.png)

1. Connect the output of the node WebEventsStream_ES to the input of the node ClickEventsFilter.

    ![](../media/lab-01/image_task08_step15.gif)

1. Click on the pencil icon of the new node Filter1 to enter edit mode. Provide the following values in the pane Filter on the left side. Then click on Save.

Field	Value
Operation name	ImpressionEventsFilter
Select a field to filter on	eventType
Keep events when the value	equals
value	IMPRESSION
    ![](../media/lab-01/image_task08_step16.png)

Note: IMPRESSION is in ALL CAPS.

It is normal that the node ImpressionEventsFilter is shown with an error. The error indicates that there is no target for the datastream coming out of the filter. We will fix this in the next step.

1. Click on + sign next to the ImpressionEventsFilter node and choose Stream from the context menu.

    ![](../media/lab-01/image_task08_step17.png)

1. Click on the pencil icon in the node Stream1 to enter edit mode. Enter ImpressionsEventsStream as name of the Eventstream in the field Stream name. Ensure that the Input data format is Json. Click on the Button Save.

    ![](../media/lab-01/image_task08_step18.png)

1. Click on + icon next to the node ImpressionEventsStream and select Eventhouse from the context menu.

    ![](../media/lab-01/image_task08_step19.png)

1. Click the pencil in node Eventhouse1 to enter edit mode. Provide the following values in the pane Eventhouse.

Field	Value
Event processing before ingestion	Ensure that this option is selected.
Destionation name	ImpressionEventStore
Workspace	Select RTI Tutorial. If you have been assigned a Workspace at the start of this lab, choose the workspace name that was provided to you.
Eventhouse	Select the Eventhouse WebEvents_EH
KQL Database	Select the KQL Database WebEvents_EH
Destination table	Click on Create new and enter BronzeImpressions as name for the new table and click on Done.
Input data format	Ensure that the option Json is selected.
1. After providing these values click on the button Save.

    ![](../media/lab-01/image_task08_step20.png)

1. Click on the button Publish that is located in the toolbar at the top of the screen.

    ![](../media/lab-01/image_task08_step21.png)

1. After a few minutes, you should see the nodes ClickEventStore and ImpressionEventStore change to mode Streaming.

    ![](../media/lab-01/image_task08_step21b.png)

1. In the end your Eventstream toplogy should look like the image below.

    ![](../media/lab-01/image_task08_step21c.png)

### Task 11: Setting up the Lakehouse
In this task we will set up the Lakehouse that will contain additional information for our usecase and in which we will also make the data from the KQL Database accessible through the lakehouse.

1. To create a Lakehouse we first have to return to the workspace where all other objects are in. To do so click on the icon RTI Tutorial in the left toolbar. If you have been assigned a Workspace at the start of this lab, choose the workspace name that was provided to you.

    ![](../media/lab-01/image_task09_step02.png)

1. Click on the button + New Item in the toolbar and in the popin window click on the tile Lakehouse.

    ![](../media/lab-01/image_task09_step03.png)

1. In the dialog New lakehouse enter WebSalesData_LH as name for the new lakehouse. Ensure that the checkbox Lakehouse schemas (Public Preview) is not checked. Then click on the button Create

    ![](../media/lab-01/image_task09_step04.png)

### Task 12: Uploading reference data files and creating delta tables in the lakehouse
After our lakehouse has been created the overview page of the lakehouse will be displayed. Next task we have to accomplish is to load static data into our new lakehouse. To do so please execute the following steps.

1. Click on the button Get data in the toolbar and select Upload Files from the dropdown menu.

    ![](../media/lab-01/image_task10_step01.png)

1. To upload the two files click on the folder symbol under Files/. Select the two files products.csv and productcategory.csv. Then click on the button Open.

    ![](../media/lab-01/image_task10_step02.png)

    >**Note:** To select the two files at once you can just hold the key CTRL while you click the two files.

1. In the popin window Upload files click on the button Upload. Now the files will be uploaded.

    ![](../media/lab-01/image_task10_step03.png)

1. To check that the files have been uploaded successfully, click on the folder Files in the pane Explorer. You should see the files in the list Files in the right part of the window.

    ![](../media/lab-01/image_task10_step04.png)

1. Next we have to create delta tables in our Lakehouse from the files we uploaded. To do this access the context menu by clicking on the three dots (...). Select Load to tables from the context menu.

    ![](../media/lab-01/image_task10_step05.png)

1. In the submenu click on New table

    ![](../media/lab-01/image_task10_step05b.png)

1. Retain all default values and click on the button Load.

    ![](../media/lab-01/image_task10_step06.png)
    >**Note:** This steps have to be executed for the file productcategory.csv as well as for the file product.csv.

1. Ensure that both files products.csv and productcategory.csv are available as delta tables in your lakehouse. Your lakehouse should look like this:

    ![](../media/lab-01/image_task10_step07.png)

### Task 13: Accessing Eventhouse data from the lakehouse 
In this task we will make the Eventhouse tables form the KQL Database available in our Lakehouse. This will be accomplished by creating shortcuts.

1. Click on the button Get data in the menu bar at the top. Choose New shortcut from the dropdown menu.

    ![](../media/lab-01/image_task11_step01.png)

    >**Note:** If your Lakehouse is using Schemas you will see the schema dbo under the folder Tables. right-click the schema dbo and select the option New table shortcut from the context menu.

1. Select **Microsoft OneLake**.

    ![](../media/lab-01/image_task11_step02.png)

1. Select the KQL Database WebEvents_EH in the Window Select a data source type and click on the button Next.

    ![](../media/lab-01/image_task11_step03.png)

1. Expand the folder Tables under WebEvents_EH in the window New shortcut and check both tables BronzeClicks and BronzeImpressions. Click on Next.

    ![](../media/lab-01/image_task11_step04.png)

1. You may return to this step to create additional shortcuts, after running the createAll.kql database script which will create additional tables. For now, you may proceed by selecting just the BronzeClicks and BronzeImpressions tables.

1. Click on the button Create.

    ![](../media/lab-01/image_task11_step05.png)

1. Now you can see the shortcuts to the tables BronzeClicks and BronzeImpressions under the folder Tables in the lakehouse WebSalesData_LH.

    ![](../media/lab-01/image_task11_step05b.png)

### Task 14: Build the KQL DB schema
In this section we will create all the silver tables, functions and enable update policies and in our Eventhouse KQL Database. Two of the tables (product and productCategory) are shortcuts to the lakehouse and the data is NOT being copied into our KQL Database.

1. Open the KQL Database WebEvents_EH in the Eventhouse of your Fabric Workspace. To do so click on the Icon of the Eventhouse in the left toolbar.

    ![](../media/lab-01/image_task12_step01.png)

1. Click on the button + New in the top toolbar and choose OneLake shortcut from the drop down menu.

    ![](../media/lab-01/image_task12_step02.png)

1. By now data has already streamed into you KQL-Database. You can see this by looking at the dashborad that is provided on the overview page of the KQL-Database    

    ![](../media/lab-01/image_task12_step02b.png)

1. Select Microsoft OneLake..

    ![](../media/lab-01/image_task12_step03.png)

1. Select the lakehouse WebSalesData_LH and click on the button Next.

    ![](../media/lab-01/image_task12_step04.png)

1. Expand the folder Tables, select the table products table and click on the button Create. This will create a shortcut to the table products in your Lakehouse without copying the data from the Lakehouse to Eventhouse.

    ![](../media/lab-01/image_task12_step05.png)

1. Repeat the steps above for the table productcategory to create a shortcut for this table as well.

1. Expand the folder Shortcuts in the tree of your Eventhouse WebEvents_EH to verify if the 2 shortcuts have been created correctly.

    ![](../media/lab-01/image_task12_step06.png)

1. Click on the button Explore your Data at the top of the screen.

    ![](../media/lab-01/image_task12_step07.png)

1. The popin window Explore your data will be shown.

    ![](../media/lab-01/image_task12_step07b.png)

1. Open the file createAll.kql in GitHub and click copy icon at the top right to copy the entire file content. This will copy the file contents to the Windows Clipboard.

    ![](../media/lab-01/image_task12_step08.png)

1. On the left side in the pane KQL Databases underneath the node WebEvents_EH there is the automatically created queryset WebEvents_EH_queryset. Click on this queryset and replace the text in the tab WebEvents_EH by the contents of the file createAll.kql. The easiest way to do this is to click in the textbox, press CTRL+A to select everything and then press CTRL+V to insert the contents from the clipboard. Then click on the Button Run

    ![](../media/lab-01/image_task12_step09.png)

1. The status of the execution of the commands from the file createAll.kql can be seen at the bottom of the pane. The result of each Command should be Completed.

    ![](../media/lab-01/image_task12_step09b.png)

1. Click on the pencil at the tab WebEvents_EH and rename the tab to createAll.

    ![](../media/lab-01/image_task12_step09c.png)

1. You can add additional tabs in the KQL Queryset to add new queries.

1. Expand all folders in the database pane on the left. All tables and functions that have been created by the script can be found here.

    ![](../media/lab-01/image_task12_step012.png)

1. While on the KQL Database details screen you may explore additional Real-Time Intelligence Samples by clicking the drop-drop next to Get data and selecting a desired sample. These samples give you the ability to learn more.

    ![](../media/lab-01/image_task12_step012b.png)

1. There are many samples from different usecases like IoT, weather analytics or Azure PlayFab game analytics.

    ![](../media/lab-01/image_task12_step012c.png)

### Task 15:  Real-Time Dashboard 
In this section, we will build a real-time dashboard to visualize the streaming data and set it to refresh every 30 seconds. (Optionally) A pre-built version of the dashboard is available to download here, which can be imported and configured to your KQL Database data source.

![](../media/lab-01/RealTimeDashboard.png)

1. Change to the workspace. To do so click on the icon of your workspace on the left pane. In our example the workspace is named RTI Tutorial. If you have been assigned a Workspace at the start of this lab, choose the workspace name that was provided to you.

    ![](../media/lab-01/image_task13_step01.png)

1. To create a new realtime dashboard click on the button + New Item and the select Real-Time Dashboard

    ![](../media/lab-01/image_task13_step02.png)

1. Enter the name Web Events Dashboard in the field New Real-Time Dashboard. Then click on Create.

    ![](../media/lab-01/image_task13_step03.png)

1. An empty dashboard will be displayed. To add a visualisation click on the button + Add tile.

    ![](../media/lab-01/image_task13_step04.png)

1. Click on the Button + Data source.

    ![](../media/lab-01/image_task13_step05.png)

1. In the Window One Lake Data Hub select the Eventhouse WebEvents_EH. Then click on Connect.

    ![](../media/lab-01/image_task13_step06.png)

1. As name keep the given name WebEvents_EH. Set the Database to WebEvents_EH and click on the button Add.

    ![](../media/lab-01/image_task13_step07.png)

1. Proceed to paste each query below, add a visual, and apply changes. (Optionally) All queries are available in this script file dashboard-RTA.kql.

    >**Note:** We will demo the steps for the very first Visual. From there on you can follow the exact same steps for all other visuals on your own.

1. This visual will show the clicks by hour. It will use the following query.

```kusto
SilverClicks
| where eventDate between (_startTime.._endTime)
| summarize date_count = count() by bin(eventDate, 1h)
| render timechart
| top 30 by date_count
```

1. Replace the content of the textbox by the code above. Click on the time range parameter at the top of the screen and set it to Last 7 days. This parameter is referenced by the query in the where clause by using fields _startTime and _endTime. Click on the button Run. The query will be executed and the results will be shown in the table at the bottom. To create a visualisation click on the button + Add Visual. This will open a pane at the right side of the browser.

    ![](../media/lab-01/image_task13_step08.png)

1. Format the visual by entering Click by hour in the field Title. Select Area chart in the combobox Visual type. Then click on the button Apply changes.

    ![](../media/lab-01/image_task13_step09.png)

1. When you click on Apply changes the value of the range parameter will jump back to one hour. Ignore this for now as we will fix this later.

1. While editing the dashboard, click on the tab Manage on the top left then click on the button Parameters.

    ![](../media/lab-01/image_task13_step10.png)

1. To edit the parameter Time range click on the pencil icon. This will enter the edit mode for this parameter.

    ![](../media/lab-01/image_task13_step11.png)

1. Select Last 7 Days in the combo box Default value. Then click on Done.

    ![](../media/lab-01/image_task13_step12.png)

1. In the parameter pane click on the button Close.

    ![](../media/lab-01/image_task13_step13.png)

1. Click on the tab Home and then click on the button New tile again to proceed with the next visuals.

    ![](../media/lab-01/image_task13_step14.png)

1. Impressions by hour 

    Visual type: Area chart.
```kusto
  //Impressions by hour
  SilverImpressions
  | where eventDate between (_startTime.._endTime)
  | summarize date_count = count() by bin(eventDate, 1h)
  | render timechart
  | top 30 by date_count
```
   ![](../media/lab-01/fabrta53.png)

1. Impressions by location

    Visual type: Map.
```kusto
//Impressions by location
SilverImpressions
| where eventDate  between (_startTime.._endTime)
| join external_table('products') on $left.productId == $right.ProductID
| project lon = toreal(geo_info_from_ip_address(ip_address).longitude), lat = toreal(geo_info_from_ip_address(ip_address).latitude), Name
| render scatterchart with (kind = map) //, xcolumn=lon, ycolumns=lat)
```

   ![](../media/lab-01/fabrta54.png)

1. Average Page Load time #
Visual type: Timechart.
```kusto
//Average Page Load time
SilverImpressions
| where eventDate   between (_startTime.._endTime)
//| summarize average_loadtime = avg(page_loading_seconds) by bin(eventDate, 1h)
| make-series average_loadtime = avg(page_loading_seconds) on eventDate from _startTime to _endTime+4h step 1h
| extend forecast = series_decompose_forecast(average_loadtime, 4)
| render timechart
```

   ![](../media/lab-01/AvgPageLoadTime.png)

1. Impressions, Clicks & CTR #
Add a tile & paste the query below once. Note, this is a multi-statement query that uses multiple let statements & a query combined by semicolons.

```kusto
//Clicks, Impressions, CTR
let imp =  SilverImpressions
| where eventDate  between (_startTime.._endTime)
| extend dateOnly = substring(todatetime(eventDate).tostring(), 0, 10)
| summarize imp_count = count() by dateOnly;
let clck = SilverClicks
| where eventDate  between (_startTime.._endTime)
| extend dateOnly = substring(todatetime(eventDate).tostring(), 0, 10)
| summarize clck_count = count() by dateOnly;
imp
| join clck on $left.dateOnly == $right.dateOnly
| project selected_date = dateOnly , impressions = imp_count , clicks = clck_count, CTR = clck_count * 100 / imp_count
```

1. Enter Impressions in the field Tile name. Select Stat in the combobox Visual type. In combobox Data Value column select impressions (long). Then click on the button Apply changes.

    ![](../media/lab-01/image_task13_step16.png)

1. Click the 3-dots (...) at the top right of the tile you just created and select Duplicate from the context menu to duplicate it two more times.

    ![](../media/lab-01/image_task13_step17.png)

1. Name the 2nd one Clicks, set the Data value column to clicks (long), then click on the button Apply changes.

    ![](../media/lab-01/fabrta57.png)

1. Name the 3rd Click Through Rate, set the Data value column to CTR, then click on the button Apply changes.

    ![](../media/lab-01/fabrta58.png)

(Optional) On the Visual formatting pane, scroll down and adjust the Conditional formatting as desired by clicking + Add rule.

1. Average Page Load Time Anomalies #
Visual type: Anomalychart

```kusto
//Avg Page Load Time Anomalies
SilverImpressions
| where eventDate   between (_startTime.._endTime)
| make-series average_loadtime = avg(page_loading_seconds) on eventDate from _startTime to _endTime+4h step 1h
| extend anomalies = series_decompose_anomalies(average_loadtime)
| render anomalychart
```

   ![](../media/lab-01/pageloadanomalies.png)

1. Strong Anomalies
Visual type: Table
```kusto
//Strong Anomalies
SilverImpressions
| where eventDate between (_startTime.._endTime)
| make-series average_loadtime = avg(page_loading_seconds) on eventDate from _startTime to _endTime+4h step 1h
| extend anomalies = series_decompose_anomalies(average_loadtime,2.5)
| mv-expand eventDate, average_loadtime, anomalies
| where anomalies <> 0
| project-away anomalies
```

1. Logo (Markdown Text Tile)
Click on the button New text tile in the toolbar at the top.

    ![](../media/lab-01/image_task13_step17b.png)

1. Paste the following code in the text area and click on the button Apply changes

```kusto
//Logo (Markdown Text Tile)
![AdventureWorks](https://vikasrajput.github.io/resources/PBIRptDev/AdventureWorksLogo.jpg "AdventureWorks")
```
   ![](../media/lab-01/image_task13_step17c.png)
   >**Note:** The title can be resized on the dashboard canvas directly, rather than writing code.

1. After you added all the visuals and moved them to thier appropiate places your dashboard should look similar to this.

    ![](../media/lab-01/image_task13_step18.png)

1. Auto-refresh
1. In this section we will enable auto-refresh so the dashboard will be automatically updated while it is shown on screen.

1. While editing the dashboard, click on the tab Manage and then click on the button Auto refresh. This will open a pane on the right side of the browser.

    ![](../media/lab-01/image_task13_step19.png)

1. In the pane Auto refresh set it to Enabled and set Default refresh rate to Continous. Then click on the button Apply

    ![](../media/lab-01/image_task13_step20.png)

1. Click on the tab Home and then click on the button Save.

    ![](../media/lab-01/image_task13_step21.png)

### Task 16: Data Activator
In this section we will create a Reflex Alert that will send a Teams Message when a value meets a certain threshold.

1. While editing the dashboard, click on the three dots (...) of the tile Click by hour. Select Set alert from the context menu. This will open the pane Set alert at the right side in the browser.

    ![](../media/lab-01/image_task14_step01.png)

1. In the pane Set alert set the values as stated in the following table

Field	Value
Check	On each event grouped by
Grouping field	event_date
When	date_count
Condition	Becomes greater than
Value	250
Select Message me in teams as Action.

   ![](../media/lab-01/image_task14_step02.png)

1. In the combobox Workspace select the workspace. In our example the workspace is named RTI Tutorial. If you have been assigned a Workspace at the start of this lab, choose the workspace name that was provided to you. Ensure that in the combobox Item the value Create a new item is selected. Insert My Reflex as value for the field New item name. Then click on the button Create.

    ![](../media/lab-01/image_task14_step03.png)

1. The Reflex item will appear in your workspace and you can edit the Reflex trigger action. The same Reflex item can also trigger multiple actions.
