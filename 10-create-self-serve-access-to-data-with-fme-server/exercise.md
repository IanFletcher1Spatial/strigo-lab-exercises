1\. Open FME Workbench

Open the workspace from [part 2](https://community.safe.com/s/article/publish-a-workspace-to-fme-server-and-run-it) in FME Workbench. Alternatively, open the template attached to this article (CommunityMapping.fmwt) in FME Workbench.

On the Generic Writer, the default writer format is set to Esri Shapefile. But, the goal is for the user to select the format of their choice, from a small list, at run time. This is accomplished with published parameters.

Parameters in FME control how FME operates. They exist in many places, such as readers, writers, and transformers.

2\. Open the Generic Writer Published Parameters

In the Navigator window, expand the GENERIC Writer by clicking the arrow to the left of it, then expand Parameters.

![navigatorpane.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2F)

Double-click the Output Format parameter, this shows that it's been set up so the user can select from any format in the formats gallery.

![currentparam.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2G)

But that's not what we want. The goal is to present the user with a list of 4 common formats. So, we will create a new user parameter and define it accordingly.

3\. Create New User Parameter

FME Desktop 2021.0 or newer:\
In the Navigator window, right-click on User Parameters and select Manage User Parameters.\
![OpenParam.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q0000028cqe)

Click on the Green plus sign then select Choice.\
![Choice.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q0000028cr8)

On the right-hand side fill in the following parameter properties:\
Parameter Identifier: Output_Format\
Prompt: Enter an output format\
Published: Enabled\
Required: Disabled\
Disable Attribute Assignment: Enabled\
Choice Configuration: Drop-down

Then for Choices enter the following:

| Value | Display |
| SHAPEFILE | Esri Shapefile |
| MITAB | MapInfo TAB |
| GML | GML |

Then select Esri Shapefile as the default value and click OK.\
![OutputFormat.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q0000028crD)

In FME Desktop 2020.2 or older:\
In the Navigator window, right-click on User Parameters and select Create User Parameter.

![createnewparam.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2H)

In the Add/Edit User Parameter dialog, enter the following parameters:

Type: Choice with Alias

Name: Output_Format

Prompt: Enter an output format:

Published: Checked

Optional: Checked

Next, click the ellipsis button for Configuration and we are going to import the formats we want the user to use.

![firstparams.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2I)

In the Edit Choice with Display Name dialog, click on Import, then Writer Formats. From here we will import the writer formats we want to use.

![importwriters.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2J)

Search and select Esri Shapefile, GML, Bentley Microstation Design V8, and MapInfo TAB (MITAB). Click OK, and OK again.

![selectformats.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2K)

Back in the Add/Edit Parameter dialog, select Esri Shapefile for the default value. The completed parameter should look like this:

![completeparams.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2L)

4\. Link Published Parameter to Output Format Parameter

Our new Output_Format parameter appears under User Parameters > Published Parameters, but we still have to link it to the Generic Writer's Output Format parameter. Locate the Output [GENERIC] Writer, and expand it with the arrow to view the Parameters, the first one being Output Format. Right-click on Output Format, select Link to User Parameter.

![linktoparam.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2M)

Select the new Output_Format parameter we just created.

![selectoutputformat.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2N)

5\. Run the workspace

If you run the workspace immediately, it will use the default value and output Esri Shapefile. However, if you select Prompt for User Parameters then click Run, you will be prompted to choose the output format. Notice only those four formats are presented now in the drop-down list. Pick GML. The workspace runs successfully.

![promptforparams.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2O)

6\. Publish Features Types to Read Parameter

Now let's set up the workspace so the user gets to choose which feature types they want to request.

In the Navigator, expand the CommunityMap [FILEGDB] File Geodatabase Reader > Parameters > and double click Features to Read. This parameter lets the user decide which feature types to process when the workspace runs. Close the dialogue.

![featuretypestoread.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2P)

Right-click on Feature Types to Read parameter and select Create User Parameter. Go with the defaults for the definition, and click OK. Confirm the new parameter appears under Published Parameters.

![modifyfeaturetypes.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2Q)

7\. Run Workspace Again

Ensure that Prompt for User Parameters is still enabled and rerun the workspace.

Notice that this time there are two parameters to set. Set it to whatever parameters you wish, and then click Run. Confirm that the workspace runs correctly.

![runwithprompt.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2R)

8\. Publish to FME Server

Now that we have the parameters set up and confirmed that the workspace runs correctly, we can publish it to FME Server.

Before publishing, save the workspace. Once saved, go to File > Publish to FME Server on the top menu bar.

Connect to the same connection as the [previous tutorial](https://community.safe.com/s/article/publish-a-workspace-to-fme-server-and-run-it). Select the Server Tutorial repository that we also created in the previous tutorial. We will keep the workspace name CommunityMapping.fmw and just overwrite the previously uploaded workspace.

Note: If you did not complete the [previous tutorial](https://community.safe.com/s/article/publish-a-workspace-to-fme-server-and-run-it), go back to the tutorial and follow the instructions in Step 3 to learn how to publish a workspace to FME Server.

8\. Open the FME Server Web User Interface

Open and log into the FME Server Web User Interface. If this is your first time logging into FME Server, please see the instructions in Tutorial: Getting Started with FME Server to learn how to do this.

9\. Run Workspace

On the side menu bar in FME Server, click on Run Workspace. On the Run Workspace page, select Server Tutorial for the Repository and the CommunityMapping workspace. Select Data Download for the Service.

Check out the Published Parameters. The two parameters that were set up and just tested in FME Workbench are shown. Just as before, select an output format, and select one or more feature types.

![publishedparamsserver.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8a&feoid=00N30000006n8wU&refid=0EM4Q000001YT2S)

Once you have selected the parameters, click Run.

10\. View the Results

The Data Download service presents a URL link to the translation results in a zip file. A quick inspection of the contents of the zip file confirms the results are what we expected.
