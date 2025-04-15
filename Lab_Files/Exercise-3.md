# Exercise 03: Integrating Eventhouse with Lakehouse
### Estimated Duration: 90 Minutes

In this exercise, you will set up a **Lakehouse** and upload reference data to create delta tables. You will access **Eventhouse data from the Lakehouse** and build a **KQL Database schema**.

## Lab Objectives: 
In this lab, you will be able to complete the following tasks:

- Task 1: Setting up the Lakehouse.
- Task 2: Create delta tables in the lakehouse.
- Task 3: Accessing Eventhouse data from the lakehouse. 
- Task 4: Build the KQL DB schema.

### Task 1: Setting up the Lakehouse
In this task, you will set up the Lakehouse containing additional information for our use case. You will also make the data from the KQL Database accessible through the Lakehouse.

1. To create a **Lakehouse**, return to your assigned workspace **RTI_<inject key="DeploymentID" enableCopy="false"></inject>** by clicking its icon in the left toolbar.

1. Click on the button **+ New Item (1)** in the toolbar. In the pop-in window click on the tile **Lakehouse (2)**.

    ![](media/image_task09_step03.png)

1. In the dialog **New Lakehouse,** enter `WebSalesData_LH` (1) as the name for the new Lakehouse. Ensure that the checkbox **Lakehouse schemas (Public Preview)** is not checked. Then click on **Create (2)**

    ![](media/image_task09_step04.png)

### Task 2: Create Delta Tables in the Lakehouse
After our Lakehouse has been created the overview page will be displayed. Next task we have to accomplish is to load static data into our new Lakehouse. To do so please follow the steps below.

1. Click on **Get data** in the toolbar and select **Upload Files** from the dropdown menu.

    ![](media/image_task10_step01.png)

1. To **upload (1)** the two files, navigate to `C:\LabFiles` and select the two files **products.csv** and **productcategory.csv** (2). Then click on **Open (3)**.

    ![](media/image_task10_step02.png)

    >**Note:** To select the two files simultaneously, you can hold the CTRL key while you click on the two files.

1. In the pop-in window **Upload files,** click on the **Upload** button. Now, the files will be uploaded.

    ![](media/image_task10_step03.png)

1. To check that the files have been uploaded successfully, click on the folder **Files** in the **Explorer** pane. You should be able to see all the files in the list **Files** located on the right part of the window.

    ![](media/image_task10_step04.png)

1. Next, we have to create delta tables in our Lakehouse from the files uploaded. To do this, access the context menu by clicking on the three dots (...). Select **Load to tables (1)** from the context menu, and in the submenu, click on **New table (2).**

    ![](media/image_task10_step05.png)

1. Retain all default values and click on the **Load** button.

    ![](media/image_task10_step06.png)
    >**Note:** These steps have to be executed for the file **productcategory.csv** as well as for the file **product.csv**.

1. Ensure that both files, **products.csv,** and **productcategory.csv,** are available as delta tables in your Lakehouse. Your Lakehouse should look like this:

    ![](media/image_task10_step07.png)

### Task 3: Accessing Eventhouse Data from the Lakehouse 
In this task, you will make the Eventhouse tables from the KQL Database available in our Lakehouse. This will be accomplished by creating shortcuts.

1. Click on the **Get data** button in the menu bar at the top. Choose a **New shortcut** from the dropdown menu.

    >**Note:** If your Lakehouse uses Schemas, you will see the **schema dbo** under the folder **Tables**. Right-click the **schema dbo** and select the option **New table shortcut** from the context menu.

1. Select **Microsoft OneLake**.

    ![](media/image_task11_step02.png)

1. Select the KQL Database **WebEvents_EH (1)** in the window, **Select a data source type,** and click on the **Next (2)** button.

    ![](media/image_task11_step03.png)

1. Expand the folder **Tables** under **WebEvents_EH** in the window **New shortcut,** and check both tables, **BronzeClicks** and **BronzeImpressions**. Click on **Next**.

    ![](media/image_task11_step04.png)

1. You may return to this step to create additional shortcuts, after running the **createAll.kql** database script, which will create additional tables. For now, you can select **BronzeClicks** and **BronzeImpressions** **(1)** tables and click on **next (2)**.

1. Click on the **Create** button.

    ![](media/image_task11_step05.png)

1. Now you can see the shortcuts to the tables **BronzeClicks** and **BronzeImpressions** under the folder **Tables** in the lakehouse **WebSalesData_LH**.

    ![](media/image_task11_step05b.png)

### Task 4: Build the KQL DB Schema
In this task, you will create all the silver tables and functions and enable updated policies in the Eventhouse KQL Database. Two of the tables (`product` and `productCategory)` are shortcuts to the Lakehouse and the data is **NOT** being copied into our KQL Database.

1. Open the KQL Database **WebEvents_EH** in the Eventhouse of your Fabric Workspace. To do so, click on the Eventhouse icon in the left toolbar.

    ![](media/image_task12_step01.png)

1. Click the button **+ New (1)** in the top toolbar and choose **OneLake shortcut (2)** from the dropdown menu.

    ![](media/image_task12_step02.png)

1. By now data has already streamed into your KQL-Database. You can see this by looking at the dashboard on the overview page of the KQL-Database.    

    ![](media/image_task12_step02b.png)

1. Select **Microsoft OneLake**.

    ![](media/image_task11_step02.png)

1. Select the lakehouse **WebSalesData_LH (1)** and click **Next (2)**.

    ![](media/image_task12_step04.png)

1. Expand the folder **Tables,** select the table **products (1)** table and click on the **Next (2)** button, then **Create** on the next page. This will create a shortcut to the table **products** in your Lakehouse without copying the data from the Lakehouse to Eventhouse.

    ![](media/image_task12_step05.png)

1. Repeat the steps above for the table **productcategory** to create a shortcut for this table as well.

1. Expand the folder **Shortcuts** in the tree of your Eventhouse **WebEvents_EH** to verify if the 2 shortcuts have been created correctly.

    ![](media/image_task12_step06.png)

1. Click on the **Query with code** button at the top of the screen.

    ![](media/image_task12_step07.png)

1. The pop-in window **Query with code** will be shown.

    ![](media/image_task12_step07b.png)

1. Copy the below code, paste it into the the Queryset, and **Run** it.

    ```kusto
    .execute database script <|
    //SILVER LAYER
    .create table SilverClicks (
        eventType:string, 
        eventID:string, 
        eventDate:datetime, 
        productId:long, 
        userAgent:dynamic, 
        device:string, 
        ip_address:string, 
        referer:dynamic, 
        page_loading_seconds:real, 
        clickType:string, 
        clickPathTitle:string, 
        clickPathUrl:string
    )
    //
    .create table SilverImpressions (
        eventType:string, 
        eventID:string, 
        eventDate:datetime, 
        productId:long, 
        userAgent:dynamic, 
        device:string, 
        ip_address:string, 
        page_loading_seconds:real, 
        relatedProductCategory:string, 
        relatedProductId:string, 
        relatedProductName:string
    )
    // use update policies to transform data during Ingestion
    .create-or-alter function with (folder="Bronze to Silver Transformations") expandClickpath()
    {
    BronzeClicks
    | mv-expand extraPayload
    | evaluate bag_unpack(extraPayload)
    | project 
        eventType, 
        eventID, 
        todatetime(eventDate), 
        productId, 
        userAgent, 
        device, 
        ip_address, 
        referer, 
        toreal(page_loading_seconds), 
        clickType = clickType, 
        clickPathTitle = ['title'], 
        clickPathUrl = url
    }
    //
    .alter table SilverClicks policy update @'[{"Source": "BronzeClicks", "Query": "expandClickpath", "IsEnabled" : true, "IsTransactional": false }]'
    //
    .create-or-alter function with (folder="Bronze to Silver Transformations") expandRelatedProducts()
    {
    BronzeImpressions
    | mv-expand extraPayload
    | evaluate bag_unpack(extraPayload)
    | project 
        eventType, 
        eventID, 
        todatetime(eventDate), 
        productId, 
        userAgent, 
        device, 
        ip_address, 
        toreal(page_loading_seconds), 
        relatedProductCategory, 
        relatedProductId, 
        relatedProductName
    }
    //
    .alter table SilverImpressions policy update @'[{"Source": "BronzeImpressions", "Query": "expandRelatedProducts", "IsEnabled" : true, "IsTransactional": false }]'
    //
    .create-or-alter function with (docstring = "Social Media Campaign Clickstream", folder = "Gold Views") SocialMediaCampaignClickstream()
    {
    SilverClicks
    | extend CampaignType = tostring(referer.campaignType)
    | extend Platform = tostring(userAgent.platform)
    | extend Browser = tostring(userAgent.browser)
    | extend RefererUrl = tostring(referer.url)
    | extend AdTitle = tostring(referer.adTitle)
    | where CampaignType in ("facebook", "twitter", "instagram", "pinterest")
    | project-away userAgent, referer
    | project-reorder CampaignType
    }
    //
    .create-or-alter function with (docstring = "Search Media Campaign Clickstream", folder = "Gold Views") SearchMediaCampaignClickstream()
    {
    SilverClicks
    | extend CampaignType = tostring(referer.campaignType)
    | extend Platform = tostring(userAgent.platform)
    | extend Browser = tostring(userAgent.browser)
    | extend RefererUrl = tostring(referer.url)
    | extend AdTitle = tostring(referer.adTitle)
    | where CampaignType in ("google", "bing")
    | project-away userAgent, referer
    | project-reorder CampaignType
    }
    //
    .create-or-alter function with (docstring = "Email Campaign Clickstream", folder = "Gold Views") EmailCampaignClickstream()
    {
    SilverClicks
    | extend CampaignType = tostring(referer.campaignType)
    | extend Platform = tostring(userAgent.platform)
    | extend Browser = tostring(userAgent.browser)
    | extend RefererUrl = tostring(referer.url)
    | extend EmailId = tostring(referer.emailId)
    | where CampaignType in ("email")
    | project-away userAgent, referer
    | project-reorder CampaignType
    }
    ```

    ![](media/image_task12_step09.png)

1. The status of the execution of the commands from the file **createAll.kql** can be seen at the bottom of the pane. The result of each Command should be **Completed**.

    ![](media/image_task12_step09b.png)

1. Click on the pencil at the tab **WebEvents_EH** and rename the tab to **createAll**.

    ![](media/image_task12_step09c.png)

1. Expand all folders in the database pane on the left. All tables and functions that have been created by the script can be found here.

    ![](media/image_task12_step012.png)


## Review

In this lab, you have completed the following:
- Created and setup up the Lakehouse.
- Create delta tables in the Lakehouse.
- Accessed Eventhouse data from the Lakehouse. 
- Built the KQL DB schema.

### You have successfully completed the exercise.
