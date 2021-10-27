1. Prepare Workspace for Publishing

Before publishing the workspace to FME Server so we can run it on the web, we can give the end-user additional control over how the workspace runs using a user parameter. Let's allow the end-user to choose the size of the buffer around construction projects. To accomplish this, double-click the Bufferer to view its parameters. Find the General > Buffer Distance parameter near top. Click the drop-down arrow, then User Parameters > Create User Parameter, then click OK to create the parameter. Click OK again to close the transformer dialog. Now the user will be prompted to enter a value for this parameter each time the workspace runs.

You can turn any parameter in your workspace into a user parameter, making your workspaces more flexible.

2. Test Published Parameter

To see this new user parameter in action, click the drop-down arrow next to the Run button to access the Run menu. Click Rerun Entire Workspace. You should see a Translation Parameter Values dialog pop up. Here, the person running the workspace can choose how much of a buffer distance to use. You can test running it with a different buffer distance, or click Cancel.

2. Publish the Workspace

To publish your workspace to FME Server, click File > Publish to FME Server.

Click the Connection drop-down and select the Training FME Server. Click Next.

Check Upload data files and click Next.

Make sure Data Download, Data Streaming, and Job Submitter are checked. Click Publish.

The workspace is published to FME Server. Look at your Translation log to find the URL to the published workspace. It will say something like:

`Direct Link         : http://localhost/fmeserver/#/workspaces/run/Training/FoodVendors.fmw`

Click the link to open the FME Server web interface.

3. Log In to FME Server

Your browser should have auto-saved your FME Server credentials. If not, please enter them and click Login:

| Username | Password     |
|----------|--------------|
| admin    | FMElearnings |

4. Configure Parameters

When you run a workspace on FME Server, you are presented with the same options as on Desktop. We can keep the default values for all the source data.

Enter 35 for Buffer Distance.

Click Run. The workspace will run on FME Server and you will be presented with a Data Download URL. Click the link and extract it to view the Excel data.

5. Continue to Next Exercise

Click the Next button below.
