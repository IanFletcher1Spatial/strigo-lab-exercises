<head><base target="_blank"> </head>
1\. Open FME Server Web User Interface and Create a New Automation

Open the FME Server Web User Interface and log in. On the side menu bar, click on Automations > Build Automation.

![automationmenu.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2c)

This opens the Automations page. Close the Get Started popup that appears. This is the automations builder; here we can create an automation to automate any FME Server task. For more information on automations, see the [Getting Started with Automations](https://community.safe.com/s/article/getting-started-with-automations).

2\. Set up Trigger

When creating a new automation, a Trigger component will already be on the canvas, you will just need to set it up. Double-click on the Trigger component to open the parameters.

![doubleclickauto.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2d)

In the Trigger parameters, we will set up a schedule. Set the Trigger to Schedule Initiated. Once the Trigger type is set, more parameters will appear.

For this schedule, we want it to run once daily at the same time. To do this, set the Schedule Type to Repeat on Interval. Then ensure Repeat Every is set to 1 day. Enable Run Immediately, this will set the Start time to every at the time you start the automation. Finally, set the End to a week from now. Click Apply once all the parameters are set.

![scheduleparams.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2e)

3\. Add and Configure an Action

With the Trigger set up, we need our schedule to do something. Double-click on the silhouetted Next Action component downstream of your new Schedule Trigger. This will open the Action parameters.

In the Action Parameters, select Run a workspace from the drop-down menu. Select Server Tutorial as the Repository and the CommunityMapping.fmw workspace will auto populate into the Workspace section as it is the only workspace in our repository.

For our parameters that we set up in the previous tutorial, set Esri Shapefile as the Output format and select DrinkingFountains as the Feature Types to Read. Once this is complete, click Apply.

![CommunityMapping.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q0000028bzL)

4\. Save and Start Automation

This automation is simple but very powerful as it allows a workspace to be run every day without the user needing to do anything beyond setting up the automation. Before the schedule is initiated, the automation needs to be saved then started.

To save the automation, click on Menu > Save As.

![saveas.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2g)

Save the automation as Scheduled Shape Updater and then click the plus sign to add a tag. Input a tag name of Server Tutorial and then click OK twice to save the automation.

![saveautomation.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2h)

Once the automation has been saved, it can be started. To start an automation, click the green Start Automation button in the top right corner. Once an automation has been started, it needs to be stopped before it can be modified.

![startautomation.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2i)

When the automation is running, there will be a red Stop Automation button where the Start Automation button was, and a banner will be at the top, stating that the automation needs to be stopped before editing.

![runningautomation.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2j)

5\. Verify that the Workspace Runs Successfully

Since you left Start Immediately checked, CommunityMapping.fmw started running when you clicked Start Automation. There are two ways to check the status of your automation and its triggered jobs.

a. View the Automation Log

From the automation page, click Menu > View Triggered Jobs. A list of jobs run by this automation appears. These jobs can also be accessed by going to Jobs > Completed.

![completedjob.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2k)

b. View the Log File

The second way to see if the automation was successful is by viewing the log files. These files can be accessed by going to Menu > View Log File while in the automation.

![logfile.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2l)

6\. Trigger a Schedule

When we set up our schedule, we enabled Run Immediately, which caused the automation to fire once we started it and then it will repeat every day at the same time as when we started the automation. But what if we wanted the workspace to be run at 3am, while we were starting the automation at 2pm, and we just wanted to test the schedule to ensure it worked.

When setting up the schedule, set the time and date to when you would like the workspace to be run, and ensure Run Immediately is unchecked. Then save and start the automation.

Once the automation has been started, if you double-click on the Schedule component to open the parameters, a Trigger button will appear at the bottom. You can't modify any of the parameters because the automation is running, but you can trigger it to initiate the schedule. This is useful for testing purposes without having to later modify the scheduled start time.

![triggerbutton.png](https://community.safe.com/servlet/rtaImage?eid=ka14Q000000lK8G&feoid=00N30000006n8wU&refid=0EM4Q000001YT2m)
