<head><base target="_blank"> </head>

#### 1\. Open FME Workbench\
In FME Workbench, open the AddressesToNotify.fmwt workspace that is attached to this article. If you completed the [Getting Started with FME Desktop tutorial](https://community.safe.com/s/article/getting-started-with-fme-desktop-translate-data-be), it is the same final workspace (GettingStarted-WriteData.fmwt).\
![WorkspaceOverview.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292lQ)

This workspace reads in water service areas for the City of Surrey, in British Columbia, then a Tester transformer is used to select the service area with a status of RED. Then using a SpatialFilter, it selects all the addresses that are within the RED water service area. After cleaning up the attributes with an AttributeManager, the customer addresses that are affected are written out to an Excel spreadsheet to be manually notified.

#### 2\. Run the Workspace\
It is always a good idea to run a workspace in FME Workbench before publishing it to FME Server because if it doesn't run in FME Workbench, it won't run in FME Server. Run the workspace and confirm it was successful. See [Getting Started with FME Desktop: Write Data](https://community.safe.com/s/article/getting-started-with-fme-desktop-write-data) to learn how to run a workspace in FME Workbench.\
It is also good practice to save the workspace before publishing.

#### 3\. Publish Workspace to FME Server\
Now that we have confirmed the workspace works, we can publish it to FME Server. With the workspace open, go to File > Publish to FME Server on the top menu bar.\
![Publish.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292lM)

*a. Add Web Connection*\
In the FME Server Publishing Wizard, we will need to set up a new connection. Click on the drop-down next to Connection and select Add Web Connection.

An FME Server Connection dialog will appear, here we will need to set the parameters to our FME Server. Set the Connection Name to something memorable, we used Training FME Server.\
Next, set up the Server URL, since we are connecting to an FME Server that is on the same machine as FME Workbench, we can use [http://localhost](http://localhost/). If you are connecting to a remote FME Server, you will need to enter the full URL. Finally, set the username and password that you used in the previous exercise to log in. Once everything is set up, click Authenticate.\
![Connection.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292lu)

Once authenticated, this connection will be available any time you publish a workspace, so you only need to create the connection once. Click Next on the connections page of the dialog to on to the next step.\
![CreateConnection .png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292lz)

* b. Create Repository*\
Now we need to create a new repository to contain our workspace. Next to Repository Name, click on the New button to create a new repository. Enter Server Tutorial for the name, and a description "Getting Started with FME Server Tutorial". Click OK.\
![CreateNewRepo.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292m4)

*c. Upload Files *\
For our workspace to run correctly, we need to upload the files. Enable Upload Files at the bottom of the dialog. After enabling it, it should state 5 files for upload. Then click Next.\
![UploadFiles.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292m9)

 When files are uploaded this way, they are stored within the repository. If you would like to upload folder files (such as geodatabases) or specify where you want the files stored, the Select Files button allows you to do that. See the [documentation](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Workbench/Workbench/Sharing_Custom_Resources.htm) for more information.

*d. Register Services*\
One last step before we can publish the workspace, we need to register it with a service. A service will control how the data will be output after the workspace is run.

The services return results in slightly different forms:

-   The Data Download Service returns results as a downloadable zip file
-   The Data Streaming Service returns results as a data stream
-   The Job Submitter Service accepts and runs workspace job requests
-   The KML Network Link returns a KML Network Link that can be used in Google Earth
-   The Notification Service allows for event-driven messaging\
For our workspace, we want to download our data at the end, so we will register with the Data Download Service. Check the Data Download Service (you can leave the Job Submitter checked), once checked, click Publish.\
![DataDownload.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292mE)

To confirm whether or not the workspace was published successfully, check the Translation Log. The Translation log will show which repository you published to, which files were included as well as a quick link to run the workspace.\
![Logfile.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292lg)

#### 4\. Open the FME Server Web Interface.\
Log in to the FME Server Web Interface using the credentials you set up in [Tour the FME Server Interface and Run a Workspace](https://community.safe.com/s/article/Tour-the-FME-Server-Interface-and-Run-a-Workspace).\
The workspace will appear in the "Last Published Workspaces" section of the home page. You may need to refresh your web interface if you had FME Server open from the previous exercise to see the workspace appear.\
![LastPublished.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292mT)

#### 5\. Run the Workspace\
You can choose to run the workspace by clicking on the AddressesToNotify.fmw in the Last Published Workspaces section or by clicking on Run Workspace on the side menu bar.

On the Run Workspaces page, select the Server Tutorial Repository. The Workspace field below will automatically be populated with the AddressesToNotify.fmw workspace because it is the only one in the repository. The Service drop-down shows the two services we registered this workspace with. Select Data Download.\
![RunWorkspace.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292mi)

If there are any published parameters in the workspace, they can be set on the run workspace page. For now, we can ignore the Source parameters, we will modify them in the [next article](https://community.safe.com/s/article/create-self-serve-access-to-data-with-fme-server). Click on Run to run the workspace.\
If you see a third parameter for Excel Output, change your Service to Data Download.

#### 6\. Review the Results Page\
After the workspace has been run, there should be a successful translation with some summary information and a data download URL.\
![FinalRun.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292mn)\
Click on the URL to download the zip file. Open up the zip file to confirm there is a Microsoft Excel file.

#### 7\. Share Workspace\
Now that we have confirmed the workspace runs successfully, we can share it with our colleagues so they can run the workspace if they need to. On the side menu click on Workspaces, this is how you can access any repository in FME Server.\
![Workspaces.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292ms)

In the Workspaces page, click on the Share button next to the Server Tutorial repository. Note that the entire contents of the repository will be shared. If you don't want to share the entire repository, you will need to move the items you wish to be shared to their own repository.\
![ShareButton.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292mx)

In the Sharing Options dialog, select the user Author and set their Permissions to Can Run. Also, select the permissions role fmeauthor and set the Permissions to Can Run. This will allow both the Author user and any other users with the fmeauthor role to only run the workspace. For more information on permissions and users see the [documentation](https://docs.safe.com/fme/html/FME_Server_Documentation/AdminGuide/AccessControl.htm?Highlight=permission).\
![SharingOptions.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lKMh&feoid=00N30000006n8wU&refid=0EM4Q00000292n7)
#### 8. Click "Next"
