<head><base target="_blank"> </head>

The final step in creating any workspace in FME is to run the workspace. Running the workspace initiates the flow of data from input through any transformers to writing the data to disk with a writer. In part six of this tutorial series, you will learn how to run a workspace to completion and view the Translation Log.

The final step before we can hand off the affected customers list is to run the workspace to create the actual file.

Continue working in the workspace from the previous exercise or open the C:/FMEData2021/Resources/GettingStarted/Workspaces/GettingStarted-WriteData-Begin.fmwt workspace.

1\.  Run the Workspace\
To run a workspace, click on the Run button. Before clicking, if you mouse over the button, a green highlight will appear around all of the objects on the canvas that will be executed when the Run button is clicked. Which objects will be run is useful to know if you are testing a workspace and have made changes recently.\
![Hover.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7r&feoid=00N30000006n8wU&refid=0EM4Q0000028bZw)

Because we've been running this workspace throughout the tutorial, only the AttributeManager and Microsoft Excel writer will run because the data is cached up to the SpatialFilter. Click on the Run button to finish running the workspace and write the data out.

Note: It is a good idea to rerun the entire workspace if you have been using feature caching. This ensures that all the data is up to date and any changes that have been made to the original dataset are reflected. To do this, click on the drop-down arrow next to Run and select Rerun Entire Workspace.\
![ReRun.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7r&feoid=00N30000006n8wU&refid=0EM4Q0000028bZx)

2\. Confirm Workspace was Successful\
After the workspace has been run, there are two main ways to tell if it was successful. The first way is to see the Feature Count numbers flow through the workflow; there should be at least one feature moving from each object.\
![TotalFeature.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7r&feoid=00N30000006n8wU&refid=0EM4Q0000028ba6)

The second way is to look for the "Translation was SUCCESSFUL" message at the bottom of the FME Workbench in the Translation Log window. This message will also note how many warnings there were and how many features were written out. The features that are written out should directly reflect the feature count number going into the writer.\
![TranslationLog.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7r&feoid=00N30000006n8wU&refid=0EM4Q0000028baG)

To access the Translation Log go to View > Windows > Translation Log. If you have saved your workspace, a saved version of the Translation Log (which has the same name as the workspace) can be accessed in the same folder as your workspace. This allows you to view the Translation Log in a text editor, like Notepad ++ if desired.

3\. Inspect the Output\
Once it has been confirmed that the "Translation was SUCCESSFUL" it is a good idea to confirm the output by either opening the output file in that format's native software or using Visual Preview within FME.

To view the final output data from this tutorial series, click on the Addresses writer feature type to show the popup menu. On the popup menu, click on the View Written Data button.\
![ViewWrittenData.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7r&feoid=00N30000006n8wU&refid=0EM4Q0000028baV)

This will open the data in the Visual Preview Window.\
Or to view the data in its native application, click on the Open Containing Folder icon, then double-click on the file to open it. The native application must be installed, in this case, Microsoft Excel.\
![OpenFolder.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7r&feoid=00N30000006n8wU&refid=0EM4Q0000028baa)\
![Excel.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7r&feoid=00N30000006n8wU&refid=0EM4Q0000028baf)

4\. Save the Workspace\
Before closing FME Workbench or starting a new workspace, be sure to save the workspace by clicking the floppy disk icon or File > Save.\
![SaveButton.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK7r&feoid=00N30000006n8wU&refid=0EM4Q0000028bak)
