<head><base target="_blank"> </head>

#### 1. Login to FME Server

Your browser should have auto-saved your FME Server credentials. If not, please enter them and click Login:

| Username | Password     |
|----------|--------------|
| admin    | FMElearnings |

#### 2. Run Workspace

A version of the workspace (with a small change) has already been published to this FME Server. Click on Run Workspace on the menu on the left of the interface.

#### 3. Configure Parameters

Workspaces in FME Server are published to repositories. Our workspace is in the Samples repository and is named FoodVendors.fmw. Use the Repository and Workspace drop-downs to select it.

When you run a workspace on FME Server, you are presented with the same options as on Desktop. We can keep the default values for all the source data.

Choose Data Download for the Service. This will return the results of the workspace in a ZIP file.

However, you can also choose to expose certain parameters to the user. This version of the workspace lets the user choose the distance for the buffer in feet.

Enter 35 for Buffer Distance.

#### 4. Run Workspace

Click Run.

The workspace will run on FME Server and you will be presented with a Data Download URL. Click the link to download the ZIP.

Extract it to view the Excel data.

It might vary from what we saw earlier because we changed the buffer distance.

#### 5. Continue to Next Exercise

Click the Next button below.
