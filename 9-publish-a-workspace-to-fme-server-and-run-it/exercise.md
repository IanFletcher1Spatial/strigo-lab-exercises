1\. Open FME Workbench

In FME Workbench, open the communitymapping.fmwt workspace that is attached to this article.

It's a straightforward workspace, taking community mapping data from a file geodatabase and writing it to the Generic format. The Generic Writer is very flexible and allows for the user to decide which format to write to when the workspace runs. Currently, it's been setup to write to Esri Shapefile. Confirm that by taking a look at the Output Format parameter in the Navigator window, or with Prompt for User Parameters selected by running the workspace.

![workspaceoverview.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT1s)

2\. Run the workspace

It is always a good idea to run a workspace in FME Workbench before publishing it to FME Server because if it doesn't run in FME Workbench, it won't run in FME Server. Run the workspace and confirm it was successful. See [Getting Started with FME Desktop: Write Data](https://community.safe.com/s/article/getting-started-with-fme-desktop-write-data) to learn how to run a workspace in FME Workbench.

It is also good practice to save the workspace before publishing as well.

3\. Publish Workspace to FME Server

Now that we have confirmed the workspace works, we can publish it to FME Server. With the workspace open, go to File > Publish to FME Server on the top menu bar.

![filepublish.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT1t)

In the Publish to FME Server dialog, we will need to set up a new connection. Click on the drop-down next to Connection and select Add Web Connection.

An FME Server Connection dialog will appear, here we will need to set the parameters to our FME Server. Set the Connection Name to something memorable, we used Training FME Server.

Next, set up the Server URL, since we are connecting to an FME Server that is on the same machine as FME Workbench, we can use http://localhost. If you are connecting to a remote FME Server, you will need to enter the full URL. Finally, set the username and password that you used in the previous exercise to log in. Once everything is set up, click Authenticate.

![connectionparams.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT1u)

Once authenticated, this connection will be available any time you publish a workspace, so you only need to create the connection once. Click Next on the connections page of the dialog to create a repository.

![connectionspage.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT1v)

Now we need to create a new repository to contain our workspace. Next to Repository Name, click on the New button to create a new repository. Enter Server Tutorial for the name, and a description "Getting Started with FME Server Tutorial". Click OK.

![createrepo.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT1w)

For our workspace to run correctly, we need to upload the files. Click on the Select Files button.

![selectfiles.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT1x)

Click on the Select Location button.

![selectlocation.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT1y)

Click the Upload to a shared resource folder button and then select the Data folder and click OK.

![selectuploadlocation.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT1z)

Select the checkbox for communitymap.gdb, then OK once more.

![selectfilestoupload.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT20)

Ensure "Upload data files" is checked and then click Next.

One last step before we can publish the workspace, we need to register a service. A service is how the data will be output after the workspace is run.

The services return results in slightly different forms:

-   The Data Download Service returns results as a downloadable zip file
-   The Data Streaming Service returns results as a data stream
-   The Job Submitter Service accepts and runs workspace job requests
-   The KML Network Link returns a KML Network Link that can be used in Google Earth
-   The Notification Service allows for event-driven messaging

For our workspace, we want to download our data at the end, so we will register with the Data Download Service. Check the Data Download Service (you can leave the Job Submitter checked), once checked, click Publish.

![downloadservice.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT21)

To confirm whether or not the workspace was published successfully, check the Translation Log.

![publishlog.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT22)

4\. Open the FME Server Web User Interface.

Log in to the FME Server Web User Interface using the credentials you set up in [Tutorial: Getting Started with FME Server](https://community.safe.com/s/article/getting-started-with-fme-server).

The workspace will appear in the "Last Published Workspaces" section of the home page.

![lastpublished.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT23)

5\. Run the Workspace

You can choose to run the workspace by clicking on the CommunityMapping.fmwt in the Last Published Workspaces section or by clicking on Run Workspace on the side menu bar.

On the Run Workspaces page, select the Repository Server Tutorial. The Workspace field below will automatically be populated with the CommunityMapping.fmw workspace because it is the only one in the repository. The Service drop-down shows the two services we registered this workspace with. Pick Data Download.

![runworkspace.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT24)

Click on Run to run the workspace once all the parameters are set.

6\. Review the Results Page

After the workspace has been run, there should be a successful translation with some summary information and a data download URL.

![resultspage.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000slOG&feoid=00N30000006n8wU&refid=0EM4Q000001YT25)

Click on the URL to download the zip file. Open up the zip file to confirm there are a number of Esri Shapefiles that result from the translation.
