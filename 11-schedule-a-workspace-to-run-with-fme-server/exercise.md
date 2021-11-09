<head><base target="_blank"> </head>

#### 1. Open FME Server Web Interface and Create a New Automation
Open the FME Server Web User Interface and log in. On the side menu bar, click on Automations > Build Automation.\
![BuildAuto.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295hR)

This opens the Automations page. Close the Get Started popup that appears. This is the automation canvas; here we can create an automation to automate any FME Server task. For more information on automations, see the [Getting Started with Automations](https://community.safe.com/s/article/getting-started-with-automations).

#### 2. Set up Trigger
When creating a new automation, a Trigger component will already be on the canvas, you will just need to set it up. Double-click on the Trigger component to open the parameters.\
![Trigger.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295hb)

In the Trigger parameters, we will set up a schedule. Set the Trigger to Schedule Initiated. Once the Trigger type is set, more parameters will appear.

For this schedule, we want it to run once daily at the same time. To do this, set the Schedule Type to Repeat on Interval. Then ensure Repeat Every is set to 1 day. Enable Start Immediately, this will set the Start time to the current time, every time you start the automation. Finally, set the End to a week from now. Click Apply once all the parameters are set.\
![Scheduleparams.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295hg)

#### 3. Add and Configure an Action
With the Trigger set up, we need our schedule to do something. Double-click on the silhouetted Next Action component connected to the success output port (the one with the checkmark); this will open the Action parameters.\
![NextAction.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295hl)

If you do not have Guides enabled, click on the orange plus sign in the bottom left corner, then click and drag an Action to the canvas. Then connect it how you would connect components in FME Workbench.\
In the Action Parameters, select Run a workspace from the drop-down menu. Select Server Tutorial as the Repository and the AddressesToNotify.fmw workspace will auto-populate into the Workspace section as it is the only workspace in our repository.\
![RunWorkspace.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295hq)

For our parameters that we set up in the [previous tutorial](https://community.safe.com/s/article/Using-Parameters-for-Self-Serve), we will need to select the uploaded update file. Click on the ellipsis next to the Service Areas Input parameter to open the file browser.\
![OpenParams.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295gy)

Then in the Resource browser, open the Data Folder, then the Server Training Folder, and select water_service_areas_updated.zip and click OK.  If you do not have this folder, go back and complete Step 11 in the [previous article](https://community.safe.com/s/article/Using-Parameters-for-Self-Serve).\
![SelectFile.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295i0)

Then select a Service Date sometime in the future. Finally, click on the ellipsis for the Destination Microsoft Excel File and browse to the Server Tutorial folder. In the lower address bar type in AddressesToNotify_updated.xlsx and click OK. Once the parameters are all set, click Apply.\
![DestinationFile.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295h3)

![FinishedParams.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295iF)

#### 4. Save and Start Automation
This automation is simple but very powerful as it allows a workspace to be run every day without the user needing to do anything beyond setting up the automation. Before the schedule is initiated, the automation needs to be saved and started.\
Click on the Start Automation button in the top right corner.\
![StartAutomation.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295iK)

Since this is the first time we are starting the automation, we will be prompted to save. Save the automation as Automate Addresses To Notify and then click the plus sign to add a Tag. Input a tag name of Server Tutorial and then click OK twice to save the automation.\
![SaveAS.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295it)

Once the automation has been saved, it will be started.  Once an automation has been started, it needs to be stopped before it can be modified.

When the automation is running, there will be a red Stop Automation button where the Start Automation button was, and a banner will be at the top, stating that the automation needs to be stopped before editing.\
![StopAutomation.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295j3)

#### 5. Verify that the Workspace Runs Successfully
Since Start Immediately is enabled, AddressesToNotify.fmw started running Start Automation was clicked. There are two ways to check the status of your automation and its triggered jobs.

*a. View the Job Log*\
From the Automation page, click Menu > View Triggered Jobs. A list of jobs run by this automation appears. These jobs can also be accessed by going to Jobs > Completed. You will know the job is from the automation because it will have the Source Type listed as Automations, as well as the name of the automation.\
![Jobs.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295jI)

*b. View the Automation Log File*\
The second way to see if the automation was successful is by viewing the log files. These files can be accessed by going to Menu > View Log File while in the automation.\
![AutomationLog.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295jN)

#### 6. Trigger a Schedule
When we set up our schedule, we enabled Run Immediately, which caused the automation to kick off once we started it, and then it will repeat every day at the same time as when we started the automation. But what if we needed a new copy of the Addresses to Notify Excel spreadsheet, but the automation isn't going to run for a few more hours based on the schedule? We can manually trigger the schedule. This option is also great for testing so you don't need to keep modifying the scheduled start time or if you have your schedule configured to run in off-hours.

Once the automation has been started, if you double-click on the Schedule component to open the parameters, a Trigger button will appear at the bottom. You can't modify any of the parameters because the automation is running, but you can trigger it to initiate the schedule.\
![TriggerSchedule.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000ogcq&feoid=00N30000006n8wU&refid=0EM4Q00000295jX)

#### 7. Click "Done"
