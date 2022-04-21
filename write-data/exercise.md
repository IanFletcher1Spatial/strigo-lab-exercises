<head><base target="_blank"> </head>

#### 1. Examine the Excel Writer

Find the "Create a Report in Excel" bookmark (on the bottom-right of the Canvas); it contains a writer feature type called AffectedVendors.

#### 2. View Connection Between Reader and Writer Feature Types

Observe that there is a dark black connection line going from the right-pointing arrow (output port) on the food vendors CSV reader feature type to the red right-pointing arrow on the Excel writer feature type. This connection line tells FME to write data to this writer feature type.

![Selected writer feature type](./images/writer-ft.png)

#### 3. Run the Workspace

Click the Run button to run the workspace and convert your CSV to Excel.

#### 4. View the Written Data

After `Translation was SUCCESSFUL` appears as the last line in your Translation Log, the workspace has finished running.

To confirm the Excel file was written, click the AffectedVendors writer feature type once to select it.

Then click the Open Containing folder icon that appears on the small toolbar above the feature type.

![Open Containing Folder](./images/open-folder.png)

The location of the new AffectedVendors.xlsx file will appear in a new Windows Explorer window. To inspect the written data, you can double-click it, and click Next through the prompts. Eventually Open Office will open the written file.

#### 5. Continue to Next Exercise

Click the Next button below.
