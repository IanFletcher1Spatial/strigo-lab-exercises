<head><base target="_blank"> </head>

FME Server comes pre-loaded with sample workspaces, which are good to use for testing various workflows. Let's run one of these sample workspaces.

#### 1\. Open the Run Workspace page

On the side menu, click on **Run Workspace**, this will open the Run Workspace page.

![](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000smiR&feoid=00N30000006n8wU&refid=0EM4Q000002WCc6)

The Run Workspace page allows you to run any workspace that has been published to FME Server. From here, we will need to set up a few more parameters before the workspace can be run.

![](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000smiR&feoid=00N30000006n8wU&refid=0EM4Q000002WCcB)

#### 2\. Choose the Samples Repository

You can think of a repository as a folder in which to store related items. FME Server comes with three repositories pre-installed: Dashboards (which contains several workspaces that run daily by default to track server performance), Tools, and Samples. We are just interested in the **Samples** repository, so select it.

![](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000smiR&feoid=00N30000006n8wU&refid=0EM4Q000002WCcG)

#### 3\. Choose which Workspace to Run

FME will narrow the workspaces down to only those in the repository that you selected. Click on the drop-down next to **Workspace** and select **austinApartments.fmw**. When the workspace is selected, it will auto-populate the Service, ensure that it was populated with **Data Streaming**. We will discuss Services in more detail when we publish our own workspace.

![](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000smiR&feoid=00N30000006n8wU&refid=0EM4Q000002WCcL)

#### 4\. Click on Run

When the job is ready, the button will turn green; click on the **run button**. After the workspace is executed by FME, the result, a kmz file in this case, will be downloaded through the browser. Feel free to view the downloaded data by opening it in [Google Earth](https://www.google.com/earth/versions/#download-pro) or [FME Data Inspector](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_DataInspector/DataInspector/Selecting_Format.htm).

![](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000smiR&feoid=00N30000006n8wU&refid=0EM4Q000002WCcQ)

#### 5. Click "Next"
